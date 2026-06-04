# ⚖️ Upgrade Cognitivo Jurídico (App de Engenharia Cognitiva)

Este é um aplicativo web unificado (Single Page Application) desenvolvido para potencializar a retenção e o aprofundamento do conhecimento jurídico. O projeto foi diretamente inspirado nas metodologias de aprendizagem e provocações epistemológicas + metodologia heutagógica + Taxonomia de Bloom + IA de Elite, aplicando conceitos de Teoria Geral do Direito à rotina de estudos.

O sistema foi desenhado sob medida para estudantes e profissionais do Direito que desejam migrar do senso comum para o rigor científico, utilizando tecnologia local e Inteligência Artificial de forma leve, fluida e com custos rigorosamente controlados.

---

## 🚀 Arquitetura e Diferenciais Técnicos

Para garantir **simplicidade, portabilidade e facilidade de manutenção**, o aplicativo adota as seguintes premissas:

1. **Single Page Application (SPA):** Todo o sistema roda em um único arquivo `html` direto no navegador. Zero dependências de servidores ou deploys complexos.
2. **Arquitetura 100% Local (LocalStorage):** O banco de dados de progresso é salvo nativamente no navegador do utilizador. Garante privacidade total e velocidade, sem pesar o cache.
3. **Custo Zero de Transcrição (Audio-to-Text):** A captura de voz utiliza a API nativa do navegador (`Web Speech API`), eliminando custos com APIs externas de transcrição (como Whisper).
4. **Controle Rigoroso de Tokens (API Key):** A integração com o modelo **Gemini 1.5 Flash** é otimizada. A IA só é acionada mediante clique em ações específicas, utilizando *System Prompts* estruturados que exigem saídas estritamente em formato JSON curto, reduzindo drasticamente o consumo de tokens.
5. **Pronto para Data Analytics (Excel / Power BI):** O app possui um módulo de exportação estruturado com tratamento de caracteres (`UTF-8 BOM`) que gera um arquivo `.csv` perfeitamente lapidado para análise estatística e dashboards de BI.

---

## 🧠 Os 3 Módulos do Aplicativo

O painel divide-se em três frentes de desenvolvimento cognitivo baseadas na palestra:

### 🎤 1. Gravador Cognitivo (O Método "Forrest Gump")
Inspirado no hábito do magistrado de correr recitando a legislação em voz alta e anotar as lacunas de memória.
* **Como funciona:** O utilizador clica em iniciar e explica um conceito jurídico (ex: horas extras, menor aprendiz) em voz alta. O navegador faz a transcrição textual.
* **O papel da IA:** Avalia o rigor científico do discurso e mapeia o "Sumário de Lacunas" — indicando conceitos ou termos técnicos essenciais que foram esquecidos ou omitidos, permitindo um estudo focado posterior.

### 🔄 2. Círculo Hermenêutico (Caso ➔ Norma ➔ Solução)
Focado no ciclo prático do raciocínio jurídico e na desconstrução do "senso comum" (a escala -1 do conhecimento explicada pelo palestrante).
* **Como funciona:** O utilizador preenche uma matriz tripartite: o **Caso** (o facto narrado pelo leigo), a **Norma** (a dogmática, fundamentação em artigos e leis) e a **Solução** (a decisão).
* **O papel da IA:** Atua como um professor rigoroso. Se o utilizador utilizar achismos ou opiniões políticas na "Norma" em vez de fundamentação legal técnica, a IA bloqueia o avanço e exige a correção. Se atingir o rigor científico, o ciclo é aprovado e guardado.

### 📊 3. Dados, Métricas e Configurações
O centro de gestão do ecossistema de aprendizagem.
* **Armazenamento Seguro:** Local para inserir a API Key do Gemini (guardada apenas no navegador do utilizador).
* **Métricas de Evolução:** Monitorização em tempo real do volume de ciclos completados.
* **Exportação:** Botão para descarregar toda a base histórica em `.csv` para alimentar relatórios estatísticos e dashboards personalizados de engenharia cognitiva.

---

## 🛠️ Como Executar o Projeto

1. Faça o download ou copie o código do arquivo `app_cognitivo.html`.
2. Dê um duplo clique no arquivo para abri-lo em qualquer navegador moderno (recomendado: *Google Chrome* ou *Microsoft Edge* para suporte completo à API de Voz).
3. Vá até a aba **3. Dados & Configurações** e cole a sua chave da API do Gemini (obtida gratuitamente ou em regime *pay-as-you-go* no Google AI Studio).
4. O seu ambiente está pronto para uso!

---

## 📊 Estrutura de Dados do Banco Local (Esquema CSV/JSON)

Cada ciclo de estudo gera um registo com as seguintes colunas estruturadas, prontas para serem mapeadas no Power BI:

| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| `data_hora` | DateTime (ISO) | Carimbo de data/hora do momento do estudo. |
| `modulo` | String | Origem do input ("Gravador Cognitivo" ou "Círculo Hermenêutico"). |
| `materia` | String | A disciplina jurídica ou tema abordado pelo utilizador. |
| `score_tecnico` | Integer (1-5) | Nota atribuída pela IA ao nível de profundidade dogmática. |
| `lacunas` | String (Separado por `;`) | Lista de termos técnicos e teorias que o utilizador omitiu. |
| `input_usuario` | Text | O texto completo transcrito ou digitado pelo utilizador. |

---

## 📝 Fundamentação Filosófica Aplicada

Este software aplica conceitos clássicos trazidos na palestra para o código:
* **Abertura da Dúvida (Louis Althusser):** O bloqueio de respostas superficiais no Módulo 2 força o utilizador a suspender as suas certezas ideológicas para ouvir e aplicar a ciência do Direito.
* **Círculo Hermenêutico:** A rotina do app estimula o movimento constante de sair da opinião individual, colidir com a explicação científica da norma e retornar a si transformado, gerando uma automatização do pensamento jurídico a conta-gotas.