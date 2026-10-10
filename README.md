# 🧮 DiscountCalculator

![Java CI](https://github.com/YESICAY/DiscountCalculator/actions/workflows/ci.yml/badge.svg)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=YESICAY_DiscountCalculator&metric=alert_status)](https://sonarcloud.io/project/overview?id=YESICAY_DiscountCalculator)

Calculadora de descuentos en **Java 25** y **Maven**, con integración continua usando **GitHub Actions**, **JaCoCo** y **SonarCloud**.

## 📌 Reglas

| Cliente | Monto  | Descuento |
|---------|--------|-----------|
| Premium | >= 500 | 20 %      |
| Premium | < 500  | 10 %      |
| Regular | >= 500 | 5 %       |
| Regular | < 500  | 0 %       |

Si el monto es `<= 0` o mayor a `1.000.000`, lanza `InvalidPurchaseException`.

## 🚀 Ejecutar

Requiere **JDK 25** y **Maven**.

```bash
mvn clean verify
```

Compila, ejecuta las pruebas y valida que la cobertura sea de al menos 95 %. El reporte queda en `target/site/jacoco/index.html`.

## ⚙️ Pipeline

En cada `push` y `pull request` a `main`, `.github/workflows/ci.yml` compila, ejecuta las pruebas con JaCoCo y envía el análisis a [SonarCloud](https://sonarcloud.io/project/overview?id=YESICAY_DiscountCalculator). Si una prueba falla, el pipeline se detiene en rojo. Requiere el secreto `SONAR_TOKEN` en GitHub.
