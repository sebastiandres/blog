---
featured: true
hide: false
toc: false
layout: post
title: "Unmerging celdas de excel"
description: "Cuando pandas se quedó corto"
categories: [balance, cuenta, reflexión]
image: images/preview/2021-11-19-streamlit.png
comments: true
---

Hace poco necesitaba procesar una gran cantidad de archivos excel que tenía muchas celdas fusionadas (merged cells). Algo así como muestro en la imagen:

![]({{ site.baseurl }}/images/2021-12-14-excel-unmerge/ejemplo.png "Excel unmerge")

Pensé que vieja confiable librería de pandas sería suficiente, pero no. Al abrir el archivo con pandas, el valor de la celda se asigna sólo a la primera:

![]({{ site.baseurl }}/images/2021-12-14-excel-unmerge/pandas1.png "Excel unmerge")

Ingenuamente intenté llenar con fillna y reemplazar los NaNs, pero el resultado no era el desado:

![]({{ site.baseurl }}/images/2021-12-14-excel-unmerge/pandas.png "Excel unmerge")

Ninguno de los métodos para llenar las celdas contiguas (`fillna` con opciones `‘backfill’, ‘bfill’, ‘pad’, ‘ffill’, None`) sirve, porque hay celdas no fusionadas que deberían mantenerse sin datos.

¿Qué hacer entonces? Después de mucho googlear, la solución correcta está dada como siempre en [stackoverflow](https://stackoverflow.com/questions/46426662/openpyxl-assign-value-to-range-of-cells-during-unmerge). La librería `openpyxl` es increíblemente flexible y permite la manipulación celda a celda:

La siguiente función removerá las celdas fusionadas copiando los valores correspondientes. Lo realizará para todas las pestañas del archivo, y marcará en rojo las celdas que fueron intervenidas:

```python
import openpyxl 
from openpyxl.styles import Alignment
from openpyxl.styles import Font

def unmerge_cells_from_file(my_file):
    """
    For a given file, opens each sheet and unmerges the cells.
    Aligns to left and highlights in red the unmerged cells.
    Saves a new excel file with the _UNMERGED suffix.
    """
    LEFT_ALIGN = Alignment(horizontal='left')
    RED_FONT = Font(color="FF0000")
    # data_only is required to evaluate the cells and store the correct value
    wb = openpyxl.load_workbook(my_file, data_only=True)
    sheets = wb.sheetnames
    for i, sheet in enumerate(sheets):
        ws = wb[sheets[i]]

        for group in ws.merged_cells.ranges:
            min_col, min_row, max_col, max_row = group.bounds
            top_left_cell_value = ws.cell(row=min_row, column=min_col).value
            if type(top_left_cell_value) == str:
                top_left_cell_value = top_left_cell_value.replace("\n", " ").replace("  ", " ")
            ws.unmerge_cells(str(group))   # you need to unmerge before writing (see explanation #1 below)
            for irow in range(min_row, max_row+1):
                for jcol in range(min_col, max_col+1):
                    cell = ws.cell(row=irow, column=jcol)
                    cell.alignment = LEFT_ALIGN
                    cell.value = top_left_cell_value
                    cell.font = RED_FONT # My addition: align to left to see if all data is there    

    output_file = my_file.replace("input", "tmp").replace(".xlsx", " UNMERGED.xlsx")
    wb.save(output_file)
    return
```

El excel resultante es el siguiente:

![]({{ site.baseurl }}/images/2021-12-14-excel-unmerge/.png "Excel unmerge")

Desde ese punto, ya es posible trabajar con pandas sin problemas.
