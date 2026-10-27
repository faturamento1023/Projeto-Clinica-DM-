# Clínica DM · Recepção

Protótipo HTML5 para o fluxo da recepção.

## Telas

- `index.html`: calendário por dia e semana, agendamentos, bloqueios e confirmação.
- `patients.html`: pesquisa e cadastro de pacientes, dados complementares e convênio.
- `schedules.html`: serviços e agendas dos profissionais, com dias e horários.
- `queue.html`: emissão, chamada, repetição e impressão de senhas.
- `display.html`: painel público para TV, com senha e sala, sem nome do paciente.

## Agendamento rápido do Dr. Diego (novembro de 2026)

- Abra `agendar.html` para escolher um dos 16 dias da escala e um horário livre.
- Horários de 30 em 30 minutos; períodos isolados conservam somente o horário informado.
- Preencha o nome e pesquise o procedimento diretamente, sem cadastro prévio.
- **Tabela Particular:** 69 serviços e preços do PDF *DM Tabela Valores Particular*, valores aprovados em 20/10/2026.
- A busca permite selecionar mais de um procedimento e ajustar quantidades, mostrando preço unitário e total automático. A tabela completa é acessível pelo botão **Tabela de preços**.
- As 16 datas e faixas horárias informadas do Dr. Diego estão carregadas no `agendar.html`. A grade usa intervalos de 30 minutos nos períodos e conserva os horários isolados.
- Esta tabela reúne os serviços da clínica, não a relação de atos executados especificamente pelo Dr. Diego. Confirme o profissional e o tempo necessário, especialmente para múltiplos exames.
- Confira os agendamentos do dia, edite, cancele e imprima.
- As alterações usam `clinica-dm-agendamentos-v1`, como a tela principal `index.html`, mas **apenas no mesmo navegador e origem**. A planilha do Google Drive **não** é sincronizada.
- **Não use dados reais de pacientes:** esta versão é um protótipo local sem login, banco compartilhado nem controles de segurança.

## Como experimentar

Sirva a pasta por HTTP (por exemplo, `python -m http.server 8000`) e abra `http://localhost:8000/`.

1. Cadastre uma agenda de profissional em **Cadastro de agendas**.
2. Cadastre um paciente em **Pacientes**.
3. Crie um agendamento em **Agenda**.
4. Em **Senhas**, abra o painel em outra aba do mesmo navegador, emita uma senha e clique em **Chamar próxima**.
5. No painel, clique em **Ativar voz e som** para permitir o anúncio por voz quando o navegador oferecer suporte.

Os dados ficam no `localStorage` do navegador. A atualização do painel usa o mesmo armazenamento e `BroadcastChannel`; portanto, este protótipo funciona entre abas no mesmo navegador e origem. A voz depende das permissões e vozes instaladas no dispositivo. Abrir os arquivos diretamente por `file://` pode isolar o armazenamento entre páginas; use HTTP.

**Não use dados reais de pacientes nesta versão.** Ainda não há login, permissões efetivas, banco compartilhado, cópia de segurança ou sincronização entre computadores. Para uso operacional na clínica, essas partes precisam ser implementadas antes de inserir dados pessoais.
