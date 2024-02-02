Salg andel = 
VAR
    tommersalg=
    CALCULATE(
        [Volum],
    dim_konto_skog[konto_s2]="10"
    )
VAR
//Beregner totalt tømmersalg som divident for alle linjer i tømmersalget
totalt_tommersalg=
    calculate(
    [Volum],
    dim_konto_skog[konto_s2]="10",
    ALL(dim_konto_skog)
    )
RETURN
DIVIDE(tommersalg,totalt_tommersalg)
