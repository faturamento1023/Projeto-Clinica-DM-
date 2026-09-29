# Clínica DM · Recepção

Protótipo HTML5 para o fluxo da recepção.

## Telas

- `index.html`: calendário por dia e semana, agendamentos, bloqueios e confirmação.
- `patients.html`: pesquisa e cadastro de pacientes, dados complementares e convênio.
- `schedules.html`: serviços e agendas dos profissionais, com dias e horários.
- `queue.html`: emissão, chamada, repetição e impressão de senhas.
- `display.html`: painel público para TV, com senha e sala, sem nome do paciente.

## Como experimentar

Sirva a pasta por HTTP (por exemplo, `python -m http.server 8000`) e abra `http://localhost:8000/`.

1. Cadastre uma agenda de profissional em **Cadastro de agendas**.
2. Cadastre um paciente em **Pacientes**.
3. Crie um agendamento em **Agenda**.
4. Em **Senhas**, abra o painel em outra aba do mesmo navegador, emita uma senha e clique em **Chamar próxima**.
5. No painel, clique em **Ativar voz e som** para permitir o anúncio por voz quando o navegador oferecer suporte.

Os dados ficam no `localStorage` do navegador. A atualização do painel usa o mesmo armazenamento e `BroadcastChannel`; portanto, este protótipo funciona entre abas no mesmo navegador e origem. A voz depende das permissões e vozes instaladas no dispositivo. Abrir os arquivos diretamente por `file://` pode isolar o armazenamento entre páginas; use HTTP.

**Não use dados reais de pacientes nesta versão.** Ainda não há login, permissões efetivas, banco compartilhado, cópia de segurança ou sincronização entre computadores. Para uso operacional na clínica, essas partes precisam ser implementadas antes de inserir dados pessoais.
