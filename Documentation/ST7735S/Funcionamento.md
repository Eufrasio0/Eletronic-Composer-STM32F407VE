# ST7735S — Tabela de Comandos

## 1. Comandos básicos / identificação

|    Hex | Comando   | Nome                         | Função                      |
| -----: | --------- | ---------------------------- | --------------------------- |
| `0x00` | NOP       | No Operation                 | Nenhuma operação            |
| `0x01` | SWRESET   | Software Reset               | Reset por software          |
| `0x04` | RDDID     | Read Display ID              | Lê identificação do display |
| `0x09` | RDDST     | Read Display Status          | Lê status do display        |
| `0x0A` | RDDPM     | Read Display Power Mode      | Lê modo de alimentação      |
| `0x0B` | RDDMADCTL | Read MADCTL                  | Lê configuração do MADCTL   |
| `0x0C` | RDDCOLMOD | Read Pixel Format            | Lê formato de pixel         |
| `0x0D` | RDDIM     | Read Display Image Mode      | Lê modo de imagem           |
| `0x0E` | RDDSM     | Read Display Signal Mode     | Lê modo de sinal            |
| `0x0F` | RDDSDR    | Read Display Self-Diagnostic | Lê diagnóstico              |

---

# 2. Modos de operação

| Hex | Comando | Nome | Função |
|---:|---|---|---|
| `0x10` | SLPIN | Sleep In | Coloca o display em Sleep |
| `0x11` | SLPOUT | Sleep Out | Sai do Sleep |
| `0x12` | PTLON | Partial Mode On | Ativa modo parcial |
| `0x13` | NORON | Normal Display Mode On | Ativa modo normal |

---

# 3. Controle da imagem

| Hex | Comando | Nome | Função |
|---:|---|---|---|
| `0x20` | INVOFF | Display Inversion Off | Desliga inversão |
| `0x21` | INVON | Display Inversion On | Liga inversão |
| `0x26` | GAMSET | Gamma Set | Seleciona configuração de gamma |
| `0x28` | DISPOFF | Display Off | Desliga o display |
| `0x29` | DISPON | Display On | Liga o display |

---

# 4. Memória / desenho

Estes são os comandos mais importantes para criar
um driver gráfico.

| Hex | Comando | Nome | Função |
|---:|---|---|---|
| `0x2A` | CASET | Column Address Set | Define intervalo X |
| `0x2B` | RASET | Row Address Set | Define intervalo Y |
| `0x2C` | RAMWR | Memory Write | Começa escrita de pixels |
| `0x2D` | RGBSET | RGB Color Set | Configuração de cores |
| `0x2E` | RAMRD | Memory Read | Lê memória gráfica |
| `0x30` | PTLAR | Partial Area | Define área parcial |
| `0x33` | VSCRDEF | Vertical Scrolling Definition | Define área de scroll |
| `0x34` | TEOFF | Tearing Effect Line Off | Desliga tearing effect |
| `0x35` | TEON | Tearing Effect Line On | Liga tearing effect |
| `0x36` | MADCTL | Memory Data Access Control | Orientação / ordem RGB |
| `0x37` | VSCSAD | Vertical Scroll Start Address | Define início do scroll |
| `0x38` | IDMOFF | Idle Mode Off | Desliga Idle Mode |
| `0x39` | IDMON | Idle Mode On | Liga Idle Mode |
| `0x3A` | COLMOD | Pixel Format Set | Define formato do pixel |

---

# 5. Comandos de memória mais importantes

## 0x2A — CASET

Column Address Set.

Define o intervalo horizontal da janela de escrita.

Formato:

```text
0x2A
X_START_HIGH
X_START_LOW
X_END_HIGH
X_END_LOW