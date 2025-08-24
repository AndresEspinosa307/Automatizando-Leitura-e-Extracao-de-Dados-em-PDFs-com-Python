# Automatizando-Leitura-e-Extracao-de-Dados-em-PDFs-com-Python
**Visão Geral do Projeto**
* Este projeto Python tem como objetivo automatizar a leitura e extração de dados específicos de múltiplos arquivos PDF (faturas/invoices) e, em seguida, organizar esses dados em uma planilha Excel. A solução é ideal para empresas que precisam processar um grande volume de documentos PDF e desejam otimizar o fluxo de trabalho de entrada de dados.

**Funcionalidades**
* Leitura de PDFs: Utiliza a biblioteca pdfplumber para abrir e extrair texto de arquivos PDF.
* Extração de Dados com Regex: Emprega expressões regulares (re) para identificar e extrair informações cruciais como "Order ID", "Shipped Date" e "Client Name" de cada fatura.
* Geração de Planilha Excel: Cria um novo arquivo Excel (.xlsx) usando a biblioteca openpyxl e popula-o com os dados extraídos.
* Estrutura de Saída: A planilha Excel gerada inclui as colunas "Order ID", "Shipped Date", "Client Name", "File Name" e "Status" para cada fatura processada.
* Tratamento de Erros: Inclui uma verificação para garantir que há arquivos PDF no diretório especificado antes de iniciar o processamento.
* Nomeação Dinâmica do Arquivo Excel: O arquivo Excel de saída é nomeado com um timestamp para evitar sobrescrita e facilitar a organização.

**Tecnologias Utilizadas**
* Python 3
* pdfplumber: Para extração de texto de PDFs.
* openpyxl: Para manipulação de arquivos Excel.
* re (módulo built-in do Python): Para expressões regulares.
* os (módulo built-in do Python): Para interagir com o sistema de arquivos.
* datetime (módulo built-in do Python): Para manipulação de datas e horas.

**Saída**
* Após a execução bem-sucedida, um arquivo Excel (.xlsx) será gerado na mesma pasta do script, com um nome no formato Invoices - YYYY-MM-DD HH-MM-SS.xlsx. Este arquivo conterá os dados extraídos de todas as faturas processadas.

**Estrutura do Código**
* O código está organizado da seguinte forma:

  * Instalação de Bibliotecas: A primeira célula instala pdfplumber e openpyxl.
  * Importações: Importa os módulos necessários (os, openpyxl, pdfplumber, re, datetime).
  * Configuração de Diretório: Define o diretório onde os PDFs estão localizados.
  * Inicialização do Excel: Cria um novo workbook e worksheet, definindo os cabeçalhos das colunas.
  * Loop de Processamento: Itera sobre cada arquivo no diretório pdf_invoices:
  * Abre o PDF e extrai o texto da primeira página.
  * Define padrões de expressões regulares para "Order ID", "Shipped Date" e "Client Name".
  * Usa re.search para encontrar os dados correspondentes.
  * Popula as células da planilha Excel com os dados extraídos ou uma mensagem de erro se o dado não for encontrado.
  * Atualiza o status para "Completed".
  * Salvamento do Arquivo Excel: Salva o workbook Excel com um nome de arquivo dinâmico baseado na data e hora atuais.

**Personalização**
* Você pode facilmente adaptar este script para extrair outros tipos de dados ou de PDFs com layouts diferentes, modificando os padrões de expressões regulares (inv_number_re_pattern, inv_date_re_pattern, inv_client_re_pattern).

**Contribuição**
* Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests para melhorias, correções de bugs ou novas funcionalidades.

**Licença**
* Este projeto está licenciado sob a Licença MIT.

