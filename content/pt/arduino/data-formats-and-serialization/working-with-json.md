---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:32.072301-07:00
description: "JSON, ou Nota\xE7\xE3o de Objeto JavaScript, \xE9 um formato leve de\
  \ troca de dados, tornando-o perfeito para armazenamento de dados ou arquivos de\
  \ configura\xE7\xE3o em\u2026"
lastmod: '2024-03-13T22:44:46.860184-06:00'
model: gpt-4-0125-preview
summary: "JSON, ou Nota\xE7\xE3o de Objeto JavaScript, \xE9 um formato leve de troca\
  \ de dados, tornando-o perfeito para armazenamento de dados ou arquivos de configura\xE7\
  \xE3o em projetos Arduino."
title: Trabalhando com JSON
weight: 38
---

## Como:
Para trabalhar com JSON em Arduino, a biblioteca `ArduinoJson` é uma escolha popular devido à sua facilidade de uso e eficiência. Ela permite analisar strings JSON, modificá-las e serializar objetos de volta em strings JSON. Veja como usá-la:

1. **Instale a biblioteca ArduinoJson**: Use o Gerenciador de Bibliotecas no IDE Arduino e instale "ArduinoJson".

2. **Desserializar uma string JSON**: Veja como analisar uma string JSON e extrair valores.

```cpp
#include <ArduinoJson.h>

const char* json = "{\"sensor\":\"gps\",\"time\":1351824120,\"data\":[48.756080,2.302038]}";

void setup() {
  Serial.begin(9600);
  StaticJsonDocument<200> doc; // Ajuste o tamanho de acordo com o documento JSON
  DeserializationError error = deserializeJson(doc, json);

  if (error) {
    Serial.print(F("deserializeJson() falhou: "));
    Serial.println(error.f_str());
    return;
  }

  const char* sensor = doc["sensor"]; // "gps"
  long time = doc["time"]; // 1351824120
  float latitude = doc["data"][0]; // 48.756080
  float longitude = doc["data"][1]; // 2.302038
  
  Serial.println(sensor);
  Serial.println(time);
  Serial.println(latitude, 6);
  Serial.println(longitude, 6);
}

void loop() {
  // Loop vazio
}
```

Saída de exemplo:

```
gps
1351824120
48.756080
2.302038
```

3. **Serializar para uma string JSON**: Veja como criar uma string JSON a partir de dados.

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc; // Ajuste o tamanho de acordo com os dados
  doc["sensor"] = "gps";
  doc["time"] = 1351824120;
  JsonArray data = doc.createNestedArray("data");
  data.add(48.756080);
  data.add(2.302038);

  serializeJson(doc, Serial);
}

void loop() {
  // Loop vazio
}
```

Saída de exemplo (formatada para legibilidade):

```
{"sensor":"gps","time":1351824120,"data":[48.756080,2.302038]}
```

Usar a biblioteca `ArduinoJson` efetivamente permite que projetos Arduino comuniquem estruturas de dados complexas em um formato legível por humanos, facilitando o desenvolvimento e a integração com serviços web.
