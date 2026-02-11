# 📉 Serverless Crypto Bot (AWS)

Bot de trading automatizado desplegado en la nube de AWS. Monitorea el precio de Bitcoin en tiempo real y almacena decisiones de compra/venta en una base de datos NoSQL.

## 🏗 Arquitectura
Este proyecto utiliza una arquitectura 100% Serverless (Pago por uso):
* **AWS Lambda (Python 3.12):** Ejecuta la lógica de extracción y análisis.
* **Amazon DynamoDB:** Persistencia de datos (Historial de precios).
* **Amazon EventBridge:** Orquestador temporal (Cron Job cada 15 min).
* **Coinbase API:** Fuente de datos financiera.

## 🚀 Cómo funciona
1.  **EventBridge** despierta a la función Lambda según el cronograma.
2.  **Lambda** solicita el precio actual de BTC a la API de Coinbase.
3.  El algoritmo compara el precio con umbrales definidos.
4.  Los datos y la decisión ("COMPRAR"/"VENDER") se indexan en **DynamoDB**.

## 🛠 Tecnologías
* Python 3.x
* AWS SDK (Boto3)
* NoSQL Database

## 📊 Estado del Proyecto
✅ Desplegado y operando en región us-east-1 (N. Virginia).
