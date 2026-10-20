# TecDash

Telemetria, saúde e otimização do PC gamer no segundo monitor, num widget Mini ou no tablet.

**[⬇ Baixar a última versão (TecDash-Setup.exe)](https://github.com/c4iolima/tecdash/releases/latest)**

## O que faz

- **Ao vivo:** FPS, frametime, 1%/0,1% low e latência (PresentMon), além de temperaturas, potências, tensões e fans (HWiNFO).
- **Modo sistema:** CPU por núcleo, composição da RAM (programas, kernel, sem dono), curva V/F da GPU com o teto do undervolt, fans × temperatura, saúde dos SSDs, consumo e custo em R$ com a bandeira tarifária da ANEEL.
- **Saúde do hardware:** desconta a temperatura de fora da sua cidade e a potência. Mostra a tendência em °C por mês, a causa provável (pasta, poeira, fan) e o antes × depois de uma troca de pasta.
- **Otimização por jogo:** gargalo medido e perfis Performance e Fidelidade com checklist. Adapta as sugestões para NVIDIA, AMD ou Intel.
- **Estabilidade:** caixa-preta de crash, teste de undervolt, regressão de driver e causa de cada engasgo (inclusive compilação de shader).
- **Avisos no celular** (ntfy ou Telegram) e integração com o Claude via MCP.

## Instalação

1. Baixe o `TecDash-Setup.exe` em [Releases](https://github.com/c4iolima/tecdash/releases/latest).
2. O Windows pode mostrar "editor desconhecido", porque o instalador não tem certificado pago. Clique em **Mais informações → Executar assim mesmo**.
3. Precisa de internet. Leva de 2 a 4 minutos. O instalador:
   - baixa o Python oficial (python.org) e o PresentMon (Intel), conferindo o SHA-256 de cada um;
   - instala e configura o HWiNFO;
   - cria o início automático e os atalhos no menu Iniciar.
4. Abra a aba **Diagnóstico** para conferir se está tudo funcionando.

Requisitos: Windows 10 ou 11, 64 bits.

Para conferir o arquivo baixado, no PowerShell: `Get-FileHash .\TecDash-Setup.exe` deve mostrar o SHA-256 publicado na Release.

## Privacidade

Tudo fica no seu PC (`C:\ProgramData\TecDash`). Só saem do computador:

- o nome da cidade, para buscar a temperatura no Open-Meteo;
- a consulta da bandeira tarifária na ANEEL;
- a verificação de nova versão aqui no GitHub;
- os avisos para o celular, se você ligar.

## Desinstalar

Menu Iniciar → **Desinstalar TecDash**. Ele pergunta se você quer manter ou apagar o seu histórico.
