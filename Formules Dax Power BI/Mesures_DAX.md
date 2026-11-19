# Power BI — Mesures DAX

## Variation Temps moyen / visite (%)

```dax
Variation Temps moyen / visite (%) =
VAR Variation = [Variation Temps moyen / visite]
RETURN
    IF(
        ISBLANK(Variation),
        BLANK(),
        IF(
            Variation > 0,
            "▲ ",
            IF(Variation < 0, "▼ ", "→ ")
        )
        & FORMAT(Variation, "+0.0%;-0.0%;0.0%")
    )
```
