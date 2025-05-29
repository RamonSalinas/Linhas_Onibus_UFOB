🚌 Sistema de Monitoramento de Atrasos de Ônibus via Mensagens de WhatsApp
📋 Descrição
Este software automatiza a análise de mensagens extraídas de grupos de WhatsApp, processando textos informais enviados espontaneamente pelos usuários para monitorar, identificar e calcular atrasos de ônibus em pontos de parada pré-definidos.

Baseia-se em um modelo de classificação supervisionada para determinar quais mensagens são relevantes para o monitoramento, além de realizar inferência sobre a localização e estimativa de atrasos com base em horários teóricos de passagem.

Todos os dados processados seguem as diretrizes da Lei Geral de Proteção de Dados (LGPD), garantindo a anonimização das informações.

🎯 Finalidade
Automatizar o processamento de mensagens informais sobre localização de ônibus.

Identificar mensagens relevantes para o monitoramento de transporte público.

Classificar, extrair e consolidar informações de atraso com base em horários previstos.

Gerar relatórios estruturados (.csv) que podem ser usados para análises e tomadas de decisão.

⚙️ Funcionalidades principais
✅ Extração automática de data, hora, telefone e mensagem.
✅ Classificação supervisionada de mensagens (válida ou não para monitoramento).
✅ Identificação de ponto de parada e linha de ônibus associada.
✅ Cálculo de horário ideal e atraso em minutos.
✅ Geração de relatórios:

relatorio_atrasos_onibus_IA.csv → Relatório detalhado.

resumo_maiores_atrasos_IA.csv → Resumo consolidado.

✅ Anonimização automática dos dados sensíveis.

🛠️ Requisitos
Python 3.8+

pandas

scikit-learn

spaCy (pt_core_news_sm)

joblib

📦 Instalação
Clone o repositório ou copie o script.

Instale as dependências:

bash
Copiar
Editar
pip install pandas scikit-learn spacy joblib
python -m spacy download pt_core_news_sm
🚀 Como Usar
Prepare o arquivo de mensagens:
Salve o histórico de mensagens do WhatsApp no formato .txt (exportado pelo próprio WhatsApp).
Exemplo de nome: /content/conversa_unificada 14 -24 de maio.txt

Treine ou carregue o modelo supervisionado:
Por padrão, o software carrega o modelo modelo_logreg.pkl.
Se quiser treinar com novos dados, ajuste a variável:

python
Copiar
Editar
REPROCESSAR_MODELO = True
E adicione o arquivo mensagens_treinamento_csv.csv com colunas mensagem e valida (0 ou 1).

Execute o script:
Ele irá automaticamente:

Processar o arquivo .txt.

Classificar mensagens válidas.

Inferir ponto, linha e atraso.

Gerar dois arquivos .csv com o resultado.

📝 Saídas esperadas
relatorio_atrasos_onibus_IA.csv: relatório completo com colunas:
data, hora, telefone, mensagem, ponto, linha, horario_ideal, atraso_minutos, datetime

resumo_maiores_atrasos_IA.csv: resumo consolidado com maiores atrasos por linha.

📊 Exemplo de Fluxo
Mensagem: "Acabei de ver o ônibus passando na praça"

Classificada como válida → ponto: "praça das corujas" → linha: "15A"

Horário teórico de passagem: 08:21 → Mensagem enviada às 08:30 → Atraso: 9 minutos

Resultado armazenado no relatório.

⚠️ Observações
O modelo pode ser re-treinado conforme a evolução dos padrões de mensagens.

Todos os dados são anonimizados automaticamente.

Pode ser adaptado para monitoramento de outros modais ou localidades.

💡 Sugestões de melhoria
Interface gráfica para upload de arquivos.

Dashboard interativo para visualizar atrasos.

Integração com sistemas de transporte público para atualização automática de horários.

👨‍🏫 Autor
Prof. Ramon Adrian Salinas Franco
Coordenação: Curso Interdisciplinar em Ciência e Tecnologia - UFOB

