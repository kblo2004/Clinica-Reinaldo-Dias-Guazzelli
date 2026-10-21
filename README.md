[LEIA-ME.txt](https://github.com/user-attachments/files/33776402/LEIA-ME.txt)
CLÍNICA — SITE HTML CORRIGIDO

1. Extraia a pasta do ZIP.
2. Abra a pasta no VS Code.
3. Abra index.html no navegador (ou use a extensão Live Server).
4. As imagens locais ficam na pasta img. Não mova index.html para fora da pasta.

Calendário: agora usa 7 colunas e mostra todos os dias da semana; sábados e domingos ficam desabilitados conforme a regra atual do site.

Atenção: a agenda compartilhada entre visitantes ainda depende da configuração correta do Supabase no código. No modo demonstração, os dados ficam apenas no navegador atual.

ATUALIZAÇÕES DESTA VERSÃO
- Serviço adicionado: Terapia do Esquema.
- Calendário: dias livres em verde, dias parcialmente ocupados em amarelo e dias lotados em vermelho. Cada dia mostra quantidade de horários ocupados (ex.: 2/4).
- Formulário de agendamento agora solicita cidade e exige confirmação da política de desistência/cancelamento com pelo menos 24 horas de antecedência.
- O painel administrativo exibe a cidade do paciente.

IMPORTANTE — SUPABASE
Para guardar a cidade no banco de dados, abra Supabase → SQL Editor e execute:

ALTER TABLE public.agendamentos
ADD COLUMN IF NOT EXISTS cidade text;

A página pública consulta somente data e horário pela view agenda_publica; não exponha nome, telefone ou cidade nessa view. O painel administrativo deve continuar protegido pelas regras de autenticação/RLS do Supabase.

No modo demonstração, a agenda salva apenas os horários no navegador e não compartilha reservas entre dispositivos. Para a agenda compartilhada funcionar, configure SUPABASE_URL e SUPABASE_ANON_KEY e confirme as permissões/RLS no Supabase.


LGPD / PRIVACIDADE
- Foi adicionada uma seção pública “Privacidade e LGPD” com referência à Lei nº 13.709/2018.
- O formulário de agendamento pede confirmação de leitura do aviso.
- O aviso é um modelo inicial: confirme os dados do controlador, fornecedores, base legal, retenção e medidas de segurança antes de publicar. O texto, isoladamente, não certifica conformidade legal ou técnica.
- Não solicite dados clínicos detalhados pelo campo de observações. Restrinja os dados dos pacientes no Supabase por autenticação e políticas RLS adequadas.

https://kblo2004.github.io/Clinica-Reinaldo-Dias-Guazzelli/
