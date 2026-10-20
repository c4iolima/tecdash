# TecDash

Telemetria, saúde e otimização do PC gamer: em tela cheia no segundo monitor, em janela (para quem tem um monitor só), num widget Mini ou no tablet.

**[⬇ Baixar a última versão (TecDash-Setup.exe)](https://github.com/c4iolima/tecdash/releases/latest)**

## O que faz

- **Resumo:** diagnóstico pronto em uma frase (saudável, atenção ou ação), o estado de cada área e as ações em ordem de prioridade.
- **Ao vivo:** FPS, frametime, 1%/0,1% low e latência (PresentMon), além de temperaturas, potências, tensões e fans (HWiNFO).
- **Modo sistema:** CPU por núcleo, composição da RAM (programas, kernel, sem dono), curva V/F da GPU com o teto do undervolt, fans × temperatura, saúde dos SSDs, consumo e custo em R$ com a bandeira tarifária da ANEEL.
- **Saúde do hardware:** desconta o clima (ou detecta quarto climatizado), a potência e a rotação das fans; mostra a tendência em °C por mês, a causa provável (pasta, poeira, fan), a confiança de cada conclusão e o antes × depois de uma troca de pasta. Limites de temperatura ajustados ao modelo da CPU e da GPU.
- **Otimização por jogo:** gargalo medido e perfis Performance e Fidelidade com checklist, usando as configurações gráficas que o jogo gravou (RDR2, Cyberpunk 2077). Adapta as sugestões para NVIDIA, AMD ou Intel.
- **Estabilidade:** caixa-preta de crash, teste de undervolt por faixa de tensão, regressão de driver e causa de cada engasgo (compilação de shader é estimada).
- **Avisos no celular** (ntfy ou Telegram) e integração com o Claude via MCP.

## Instalação

1. Baixe o `TecDash-Setup.exe` em [Releases](https://github.com/c4iolima/tecdash/releases/latest).
2. O Windows pode mostrar "editor desconhecido", porque o instalador não tem certificado pago. Clique em **Mais informações → Executar assim mesmo**.
3. Leva de 1 a 2 minutos. O instalador já traz o Python e o PresentMon; só o HWiNFO é baixado (pelo winget). Ele:
   - instala e configura o HWiNFO;
   - cria o início automático e os atalhos no menu Iniciar;
   - confere se o TecDash abriu (numa atualização que falhar, volta sozinho para a versão anterior).
4. Na primeira vez abre um assistente de 7 passos (inclui escolher o painel em janela ou tela cheia; com um monitor só, o padrão é janela). Depois, a aba **Resumo** mostra como está o PC.

Requisitos: Windows 10 ou 11, 64 bits. Instalação silenciosa: `TecDash-Setup.exe /S` (`/SEMHWINFO` não mexe no HWiNFO).

Para conferir o arquivo baixado, no PowerShell: `Get-FileHash .\TecDash-Setup.exe` deve mostrar o SHA-256 publicado na Release.

## Privacidade

Tudo fica no seu PC (`C:\ProgramData\TecDash`, com backup diário do histórico). Só saem do computador:

- o nome da cidade, para buscar a temperatura no Open-Meteo;
- a consulta da bandeira tarifária na ANEEL;
- a verificação de nova versão aqui no GitHub;
- os avisos para o celular, se você ligar.

O pacote de suporte (aba Diagnóstico) é gerado no seu PC, com tokens mascarados, e só sai se você enviar.

## Desinstalar

Menu Iniciar → **Desinstalar TecDash**. Ele pergunta se você quer manter ou apagar o seu histórico.

Licença MIT. Componentes de terceiros em `LICENCAS-TERCEIROS.txt` na pasta de instalação.
