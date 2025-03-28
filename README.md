# Apache Kafka

## Que es Apache Kafka ?

Apache Kafka es una plataforma de transmision de datos distribuidos que puede publicar, suscribirse, almacenar y precesar transmisiones de registros en tiempo real. Esta diseñado para manejar flujos de datos de multiples fuentes y entregarlos a multiples consumidores.

Kafka tiene una arquitectura de productor-consumidor, que permite que los productores de datos publiquen mensajes a un canal (denominado topic), y los consumidores reciban esos mensajes para procesarlos.

## ¿Dónde se usa Apache Kafka?

Apache Kafka se utiliza en una variedad de contextos, especialmente cuando se requiere manejar flujos de datos en tiempo real. Algunos de los casos más comunes son:

- **Monitoreo de aplicaciones**: Kafka se usa para recopilar y transmitir logs o métricas de aplicaciones en tiempo real. Las empresas pueden recolectar logs de múltiples servicios y analizarlos en tiempo real para detectar fallos o problemas de rendimiento.

- **Análisis en tiempo real**: Muchas empresas utilizan Kafka para transmitir datos en tiempo real a sistemas de análisis. Por ejemplo, en aplicaciones de análisis de Big Data donde se procesan grandes cantidades de datos desde sensores o redes sociales para obtener insights instantáneos.

- **Integración de datos**: Kafka se usa como sistema central de mensajería para integrar diferentes sistemas en una arquitectura de microservicios. Permite que diferentes servicios se comuniquen entre sí mediante flujos de mensajes, lo cual es común en arquitecturas orientadas a eventos.

- **Sistemas de recomendación**: Plataformas como Netflix o Spotify utilizan Kafka para transmitir eventos en tiempo real, como las acciones de los usuarios (por ejemplo, reproducción de contenido), y luego usar esos eventos para generar recomendaciones personalizadas.

- **IoT (Internet de las Cosas)**: Kafka es muy utilizado en aplicaciones de IoT donde se requiere transmitir, procesar y almacenar datos provenientes de dispositivos conectados en tiempo real. Kafka maneja eficientemente los flujos de datos provenientes de sensores.


## Ventajas de usar Apache Kafka
- **Escalabilidad**: Kafka puede manejar millones de mensajes por segundo y se puede escalar horizontalmente añadiendo más brokers y particiones.

- **Alta disponibilidad y tolerancia a fallos**: Kafka asegura que los mensajes se distribuyan a través de varios brokers, lo que permite la replicación y la recuperación en caso de fallos.

- **Persistencia de mensajes**: Kafka almacena los mensajes de manera eficiente durante un periodo de tiempo configurable, lo que permite la recuperación de mensajes antiguos.

- **Rendimiento alto**: Kafka es extremadamente rápido, lo que lo hace adecuado para aplicaciones que requieren el procesamiento de datos en tiempo real con latencia mínima.

## Requisitos

    - Java
    - Gradle
    - Docker

### **Clonar el repositorio**

```sh
git clone https://github.com/ronaldo-mendoza-jalafund/ApacheKafka.git
```


### Demo

```sh
docker-compose up -d
```

Corremos el proyecto

```sh
./gradlew bootRun
```

#### **Ver por la web**

```sh
http://localhost:8080/api/v1/kafka/publish?message=HelloKafka
```

#### **Ver por consola**

Ingresamos a la consola

```sh
docker exec -it kafka /bin/sh
```

Creamos 2 ventanas aparte

*Producer*

```sh
kafka-console-producer --broker-list localhost:9092 --topic test
```
*Consumer*

```sh
kafka-console-consumer --bootstrap-server localhost:9092 --topic test --from-beginning
```

*Verificacion de servidor Kafka*

```sh
kafka-topics --bootstrap-server localhost:9092 --list
```