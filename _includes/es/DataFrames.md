Para herramientas tipo `dplyr`, consulte
[DataFramesMeta.jl.](https://github.com/JuliaStats/DataFramesMeta.jl)

|                                           |                                           |
| ----------------------------------------- | ----------------------------------------- |
| Leer Stata, SPSS, etc.                    | Paquete `StatFiles`                       |
| <a class="tooltip" href="#">Describir<span>Similar a `summary(df)` en R.</span></a> data frame | `describe(df)` |
| Hacer de la columna `col` un vector       | `v = df[:col]`                            |
| Ordenar por `col`                         | `sort!(df, [:col])`                       |
| <a class="tooltip" href="#">Datos categóricos<span>Similar a `df$col = as.factor(df$col)` en R.</span> `col` | `categorical!(df, [:col])` |
| Listar niveles `col`                      | `levels(df[:col])`                        |
| Todas las observaciones con `col==val`    | `df[df[:col] .== val, :]`                 |
| Redimensionar de formato ancho a largo    | `stack(df, [1:n; ])`<br>`stack(df, [:col1, :col2, ...]`<br>`melt(df, [:col1, :col2]) [` |
| Redimensionar de formato largo a ancho    | `unstack(df, :id, :val)`                  |
| Hacer `Nullable`                          | `allowmissing!(df)` or `allowmissing!(df, :col)` |
| Bucle sobre Filas                         | `for r in eachrow(df)`<br>`    # bloque de código.`<br>`    # r es un Struct con los nombres de campos de col.`<br>`end` |
| Bucle sobre Columnas                      | `for c in eachcol(df)`<br>`    # bloque de código.`<br>`    # c es un tuple con nombre y vector`<br>`end` |
| Aplicar func a grupos                     | `by(df, :group_col, func)`                |
| Consulta                                  | `using Query`<br>`query = @from r in df begin`<br>`    @where r.col1 > 40`<br>`    @select {new_name=r.col1, r.col2}`<br>`    @collect DataFrame # Default: iterator`<br>`end` |
