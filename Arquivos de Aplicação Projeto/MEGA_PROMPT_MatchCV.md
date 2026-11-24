# MEGA PROMPT — MATCHCV | Plataforma Inteligente de Análise e Otimização de Currículos

## 1. Visão geral do projeto

Desenvolva uma aplicação web SaaS chamada **MatchCV**, uma plataforma inteligente que compara currículos com descrições de vagas de emprego, identifica oportunidades de melhoria e gera versões otimizadas para sistemas de recrutamento ATS (*Applicant Tracking Systems*).

O objetivo é permitir que qualquer pessoa compreenda o quanto seu currículo está alinhado a uma vaga e consiga melhorar sua apresentação profissional de maneira estratégica, transparente e verdadeira.

A aplicação deve ter uma experiência moderna, intuitiva, responsiva e profissional, com foco em usabilidade, clareza das informações e facilidade de navegação.

**Atenção: não construa apenas um protótipo visual.** Implemente uma aplicação funcional, com autenticação, persistência real dos dados, processamento por inteligência artificial, geração de documentos e dashboard integrado ao banco de dados.

O idioma padrão de toda a aplicação será **português do Brasil (pt-BR)**.

### Regra fundamental do produto

A aplicação deve melhorar a maneira como o candidato apresenta suas experiências, competências e qualificações, mas nunca inventar informações.

**O MatchCV não cria experiências profissionais, habilidades, certificações, cursos, empresas, cargos, resultados ou qualificações que o candidato não informou.**

A inteligência artificial pode reorganizar, corrigir, resumir e aprimorar a escrita do currículo. Também pode recomendar palavras-chave ausentes, mas jamais inseri-las como competências comprovadas sem evidências fornecidas pelo usuário.

Exibir essa política de transparência na interface, especialmente durante a análise e na geração do currículo:

> Nosso compromisso é valorizar sua trajetória profissional, não inventá-la. O MatchCV melhora a apresentação das suas qualificações, mas nunca cria experiências, habilidades ou resultados que você não possui.

---

## 2. Objetivos principais

Desenvolver uma plataforma que permita:

1. Inserir uma descrição de vaga por meio de um campo de texto.
2. Inserir o currículo atual por meio de outro campo de texto.
3. Analisar a compatibilidade entre o currículo e a vaga.
4. Gerar uma pontuação de compatibilidade em percentual.
5. Identificar palavras-chave encontradas no currículo.
6. Identificar palavras-chave importantes que estão ausentes.
7. Apresentar pontos fortes e oportunidades de melhoria.
8. Gerar uma versão otimizada do currículo, seguindo padrões ATS.
9. Permitir visualizar, editar e copiar o currículo otimizado.
10. Exportar o currículo em formato `.docx`.
11. Salvar análises, versões e resultados no banco de dados.
12. Criar autenticação de usuários com confirmação de e-mail via Resend.
13. Desenvolver um dashboard para acompanhar a evolução das pontuações.
14. Permitir selecionar um nicho profissional, especialmente Tecnologia e Primeiro Emprego.
15. Implementar SEO e GEO para melhorar a descoberta da plataforma nos mecanismos de busca tradicionais e nas ferramentas de busca baseadas em inteligência artificial.

---

## 3. Stack tecnológica e arquitetura

Utilize uma arquitetura moderna, organizada, escalável e adequada à construção de um SaaS.

### Front-end

- React.
- TypeScript.
- Vite.
- Tailwind CSS.
- Shadcn/ui como design system principal.
- Lucide React para ícones.
- Recharts para gráficos e visualizações.
- React Hook Form para gerenciamento de formulários.
- Zod para validação de dados.
- React Router para navegação.

### Back-end e infraestrutura

- Supabase como backend principal.
- Supabase Auth para autenticação.
- PostgreSQL para armazenamento dos dados.
- Supabase Edge Functions para operações seguras no servidor.
- Row Level Security (RLS) para proteção dos dados.
- Resend para envio de e-mails transacionais e confirmação de cadastro.
- Serviço de inteligência artificial integrado por meio de API, com chamadas realizadas exclusivamente no servidor.
- Biblioteca `docx` para geração dos documentos Word.

### Segurança das integrações

Todas as chaves de API devem ser armazenadas em variáveis de ambiente ou secrets no ambiente seguro do projeto.

Nunca expor no front-end:

- Chave da API de inteligência artificial.
- `RESEND_API_KEY`.
- `SUPABASE_SERVICE_ROLE_KEY`.
- Credenciais administrativas.
- Tokens privados de integração.

Não simular integrações. Caso alguma credencial precise ser configurada manualmente no Supabase ou no Lovable, implementar a estrutura correspondente e apresentar instruções claras de configuração.

---

## 4. Identidade visual e Design System

Utilize **Shadcn/ui como base obrigatória do design system**, com componentes reutilizáveis e consistentes.

A identidade visual deve transmitir tecnologia, inteligência, confiança, produtividade e inovação.

O visual deve combinar fundos escuros elegantes, superfícies claras ou levemente contrastantes, cores vibrantes para destacar informações e elementos visuais que facilitem a compreensão dos resultados.

### 4.1. Paleta de cores

Adote a seguinte identidade:

| Aplicação | Cor | Código |
|---|---|---|
| Fundo principal escuro | Midnight Navy | `#0B1020` |
| Superfícies escuras | Deep Slate | `#151D32` |
| Superfícies claras | White | `#FFFFFF` |
| Cor primária | Electric Violet | `#7C3AED` |
| Cor secundária | Cyan | `#06B6D4` |
| Destaque positivo | Lime Green | `#84CC16` |
| Destaque de atenção | Amber | `#F59E0B` |
| Destaque negativo | Coral Red | `#F43F5E` |
| Texto principal escuro | Slate | `#1E293B` |
| Texto secundário | Muted Slate | `#64748B` |
| Bordas | Light Slate | `#E2E8F0` |

Utilize gradientes discretos entre violeta e ciano em elementos estratégicos, como botões principais, indicadores de compatibilidade e destaques do dashboard.

### 4.2. Aplicação das cores

- Violeta: ações principais, inteligência artificial e funcionalidades centrais.
- Ciano: informações, palavras-chave e indicadores analíticos.
- Verde: compatibilidade elevada, pontos positivos e melhorias.
- Amarelo: atenção, recomendações e requisitos parcialmente atendidos.
- Vermelho: lacunas relevantes e problemas que exigem atenção.
- Cinza: informações secundárias e conteúdos auxiliares.

Não dependa exclusivamente das cores para comunicar estados. Utilize também textos, ícones e descrições acessíveis.

### 4.3. Componentes Shadcn/ui

Utilize componentes padronizados para garantir consistência:

- Button.
- Card.
- Input.
- Textarea.
- Label.
- Badge.
- Progress.
- Tabs.
- Dialog.
- AlertDialog.
- Tooltip.
- DropdownMenu.
- Select.
- Separator.
- Skeleton.
- Table.
- Accordion.
- Sheet.
- Sidebar.
- Avatar.
- Toast ou Sonner.
- Chart, quando aplicável.

### 4.4. Diretrizes visuais

- Interface limpa e organizada.
- Hierarquia visual clara.
- Bordas arredondadas moderadamente.
- Sombras discretas.
- Espaçamento consistente.
- Tipografia moderna e legível.
- Microinterações suaves.
- Estados visuais de carregamento.
- Feedback imediato após ações.
- Ícones Lucide com utilização consistente.
- Layout responsivo para computadores, tablets e celulares.

Criar também um modo claro e um modo escuro, respeitando a identidade visual e mantendo contraste adequado.

---

## 5. Estrutura de navegação

Criar uma navegação principal com sidebar no dashboard.

### Menu lateral

1. Visão geral.
2. Nova análise.
3. Histórico de análises.
4. Meus currículos.
5. Evolução do match.
6. Configurações.
7. Meu perfil.
8. Sair.

### Cabeçalho

O cabeçalho deve conter:

- Logotipo MatchCV.
- Identificação do usuário.
- Avatar.
- Menu de perfil.
- Acesso às configurações.
- Alternância entre tema claro e escuro.

No celular, transformar a sidebar em menu retrátil.

---

## 6. Telas e funcionalidades

### 6.1. Página inicial — Landing Page

Criar uma landing page moderna, comercial e otimizada para conversão.

#### Hero Section

Título principal:

**Seu próximo emprego começa com um currículo mais estratégico.**

Subtítulo:

Compare seu currículo com uma vaga, descubra quais competências estão faltando e gere uma versão otimizada para sistemas ATS com inteligência artificial.

Botão principal:

**Analisar meu currículo**

Botão secundário:

**Como funciona**

Adicionar uma representação visual do produto mostrando:

- Um currículo.
- Uma descrição de vaga.
- Um indicador de compatibilidade.
- Palavras-chave encontradas e ausentes.
- Um exemplo de currículo otimizado.

#### Seção: Como funciona

Apresentar três etapas:

**1. Insira seus dados**

Cole seu currículo e a descrição da vaga desejada.

**2. Descubra seu nível de compatibilidade**

A inteligência artificial analisa requisitos, competências e palavras-chave.

**3. Otimize seu currículo**

Gere uma versão mais estratégica, organizada e compatível com padrões ATS.

#### Seção: Funcionalidades

Apresentar cards para:

- Análise inteligente de currículos.
- Comparação com vagas.
- Identificação de palavras-chave.
- Otimização ATS.
- Exportação em Word.
- Histórico e evolução do desempenho.

#### Seção: Transparência e confiança

Destacar:

**Sua experiência é sua. Nossa função é apresentá-la melhor.**

Explicar que o sistema não inventa experiências ou qualificações e que todas as sugestões precisam respeitar a trajetória real do candidato.

#### Seção: Perguntas frequentes

Criar perguntas e respostas sobre:

- O que é um currículo ATS?
- Como funciona o cálculo de compatibilidade?
- A ferramenta pode inventar experiências?
- Posso editar o currículo gerado?
- Como exportar meu currículo?
- Meus dados ficam protegidos?
- O MatchCV garante uma entrevista?

Informar claramente que a pontuação é uma estimativa orientativa, não uma garantia de aprovação em processos seletivos.

#### Footer

Incluir:

- Sobre o MatchCV.
- Como funciona.
- Política de privacidade.
- Termos de uso.
- Contato.
- Direitos autorais.

### 6.2. Cadastro e autenticação

Criar sistema completo de autenticação utilizando Supabase Auth.

#### Tela de cadastro

Campos:

- Nome completo.
- E-mail.
- Senha.
- Confirmação de senha.
- Checkbox de aceite dos termos de uso e política de privacidade.

Botão:

**Criar minha conta**

Após o cadastro:

1. Criar o usuário no Supabase Auth.
2. Enviar e-mail de confirmação utilizando Resend como serviço de envio.
3. Exibir mensagem informando que o usuário precisa confirmar seu endereço de e-mail.
4. Permitir reenviar o e-mail de confirmação.
5. Liberar o acesso à área autenticada somente após a confirmação, conforme a configuração do Supabase Auth.

#### Integração Resend

Implementar a integração segura entre Supabase Auth e Resend.

Utilizar a configuração de SMTP personalizado do Supabase Auth com as credenciais SMTP disponibilizadas pelo Resend, ou o mecanismo de integração oficialmente suportado pelo ambiente.

Configurar:

- Nome do remetente: MatchCV.
- Assunto: Confirme seu cadastro no MatchCV.
- Template de confirmação com identidade visual da aplicação.
- Link seguro de confirmação.
- Mensagem de boas-vindas após a confirmação.

O envio precisa ser real. Não simular a confirmação de e-mail.

Caso sejam necessárias configurações externas, documentar quais informações devem ser inseridas no painel do Supabase e do Resend.

#### Login

Campos:

- E-mail.
- Senha.

Recursos adicionais:

- Esqueci minha senha.
- Recuperação de acesso.
- Exibir ou ocultar senha.
- Mensagens de erro claras.
- Redirecionamento após autenticação.

#### Proteção das páginas

Usuários não autenticados não poderão acessar o dashboard, histórico, currículos ou análises.

Criar rotas protegidas e controle de sessão.

### 6.3. Dashboard — Visão geral

Criar um dashboard profissional com informações relevantes e atualizadas de acordo com os registros reais do usuário.

#### Cards de indicadores

Apresentar:

**Total de análises**

Quantidade total de análises realizadas.

**Match médio**

Média das pontuações registradas pelo usuário.

**Melhor compatibilidade**

Maior percentual de compatibilidade alcançado.

**Currículos otimizados**

Quantidade de versões de currículos geradas.

#### Gráfico de evolução

Criar gráfico de linhas utilizando Recharts.

Título:

**Evolução da compatibilidade dos seus currículos**

Eixo horizontal: datas das análises.

Eixo vertical: percentual de compatibilidade.

O gráfico deve mostrar a evolução do match ao longo das versões analisadas para uma mesma vaga.

Permitir selecionar uma oportunidade para visualizar sua evolução individual.

#### Distribuição de palavras-chave

Criar gráfico ou indicadores para:

- Palavras-chave encontradas.
- Palavras-chave ausentes.
- Requisitos atendidos.
- Requisitos parcialmente atendidos.

#### Histórico recente

Exibir tabela com:

- Cargo analisado.
- Empresa, quando informada.
- Data da análise.
- Percentual de match.
- Versão do currículo.
- Ação para visualizar detalhes.

Criar estados vazios quando o usuário ainda não possuir análises.

Exemplo:

**Você ainda não realizou nenhuma análise.**

Comece comparando seu currículo com uma vaga para acompanhar sua evolução.

Botão: **Criar primeira análise**.

---

## 7. Tela principal — Nova análise

Esta é a funcionalidade central do MatchCV e deve receber prioridade máxima de desenvolvimento.

Criar uma interface simples, intuitiva e organizada em etapas.

### 7.1. Seleção de nicho

Antes de iniciar a análise, permitir selecionar o perfil profissional:

- Geral.
- Tecnologia.
- Primeiro emprego.
- Estágio.
- Administrativo.
- Comercial.
- Outro.

A seleção deverá influenciar a interpretação do currículo e as recomendações geradas pela inteligência artificial, sem alterar ou inventar informações.

Permitir mudar o nicho durante futuras análises.

### 7.2. Campo de descrição da vaga

Título:

**Descrição da vaga**

Orientação:

Cole abaixo a descrição completa da oportunidade para a qual deseja se candidatar.

Campo de texto amplo, com suporte a múltiplas linhas.

Placeholder:

Cole aqui a descrição da vaga, incluindo responsabilidades, requisitos, competências e qualificações desejadas...

Permitir informar opcionalmente:

- Nome da empresa.
- Cargo pretendido.

### 7.3. Campo de currículo

Título:

**Seu currículo atual**

Orientação:

Cole o conteúdo do seu currículo para que possamos comparar suas qualificações com a vaga.

Campo de texto amplo.

Placeholder:

Cole aqui seu currículo completo, incluindo resumo profissional, experiências, formação acadêmica, competências, cursos e certificações...

Permitir inserir texto de forma simples, preservando quebras de linha.

O MVP deve priorizar a colagem de texto. A arquitetura poderá permitir o suporte a arquivos futuramente, mas não deve tornar essa funcionalidade obrigatória para concluir o fluxo principal.

### 7.4. Validação

Antes da análise:

- Verificar se a descrição da vaga foi preenchida.
- Verificar se o currículo foi preenchido.
- Verificar se os textos possuem conteúdo suficiente para análise.
- Informar erros próximos aos respectivos campos.
- Exibir orientação para não inserir informações pessoais desnecessárias.
- Solicitar consentimento para o processamento dos dados pela inteligência artificial.

Botão principal:

**Analisar compatibilidade**

Durante o processamento, mostrar:

1. Analisando a descrição da vaga.
2. Identificando requisitos e competências.
3. Comparando com seu currículo.
4. Calculando compatibilidade.
5. Preparando recomendações.

Utilizar animações discretas e barra de progresso ou indicadores de etapa.

Não apresentar resultados fictícios enquanto a análise estiver em andamento.

---

## 8. Motor de análise inteligente

Implementar uma funcionalidade de inteligência artificial que compare os dois textos e produza resultados estruturados.

O processamento deve ocorrer no servidor, por meio de Supabase Edge Functions, utilizando um provedor de IA configurado por variável secreta.

Validar a resposta da IA com Zod antes de armazenar os resultados.

### 8.1. Critérios de análise

O sistema deve identificar:

- Cargo e nível profissional da oportunidade.
- Responsabilidades principais.
- Requisitos obrigatórios.
- Requisitos desejáveis.
- Competências técnicas.
- Competências comportamentais.
- Ferramentas e tecnologias.
- Formação acadêmica exigida.
- Certificações mencionadas.
- Experiência profissional solicitada.
- Palavras-chave estratégicas.

Em seguida, identificar quais desses requisitos aparecem no currículo.

### 8.2. Cálculo do match

Gerar uma pontuação de compatibilidade entre 0% e 100%.

Utilizar um cálculo transparente e reproduzível, considerando:

| Critério | Peso inicial |
|---|---:|
| Palavras-chave e competências | 40% |
| Requisitos técnicos e funcionais | 30% |
| Experiências e responsabilidades relacionadas | 20% |
| Formação e certificações exigidas | 10% |

Quando a vaga não apresentar exigências de determinada categoria, redistribuir proporcionalmente o peso entre os critérios aplicáveis.

A pontuação deve considerar evidências presentes no currículo. Não conceder pontos por uma competência que o candidato não demonstrou possuir.

A análise semântica pode identificar equivalências entre termos diferentes, mas deve distinguir:

- Correspondência literal.
- Correspondência equivalente ou semântica.
- Correspondência parcial.
- Requisito não identificado.

Não apresentar a pontuação como uma previsão exata do comportamento de sistemas ATS reais.

#### Faixas visuais de compatibilidade

| Pontuação | Classificação |
|---|---|
| 0% a 39% | Baixa compatibilidade |
| 40% a 59% | Compatibilidade moderada |
| 60% a 79% | Boa compatibilidade |
| 80% a 100% | Alta compatibilidade |

Essas classificações são orientativas e não representam critérios universais de recrutamento.

### 8.3. Estrutura do resultado da IA

A Edge Function deverá validar e retornar um objeto estruturado contendo:

- Título da vaga.
- Nicho selecionado.
- Pontuação geral.
- Pontuação por critério.
- Requisitos identificados na vaga.
- Palavras-chave encontradas.
- Palavras-chave ausentes.
- Correspondências parciais.
- Principais pontos fortes.
- Lacunas identificadas.
- Recomendações de melhoria.
- Resumo da análise.
- Alertas sobre informações que não devem ser presumidas.

Utilizar um formato JSON consistente, com campos tipados e validação obrigatória.

Se a resposta da IA estiver incompleta ou inválida, apresentar erro controlado e permitir uma nova tentativa sem salvar uma análise inconsistente.

---

## 9. Tela de resultados da análise

Após o processamento, apresentar uma página organizada e visualmente atraente.

### 9.1. Indicador principal de match

Exibir um card de destaque com:

**Seu nível de compatibilidade**

Representar o percentual por meio de um gráfico circular, indicador radial ou Progress personalizado.

Exemplo ilustrativo de apresentação: 78%.

O número apresentado deverá vir exclusivamente do resultado efetivo da análise.

Exibir também a classificação correspondente.

### 9.2. Pontuação detalhada

Criar cards ou barras de progresso para:

- Palavras-chave e competências.
- Requisitos técnicos e funcionais.
- Experiências relacionadas.
- Formação e certificações.

Mostrar o percentual individual de cada critério, com uma breve explicação.

### 9.3. Palavras-chave encontradas

Título:

**O que seu currículo já contempla**

Exibir badges verdes ou cianos com as palavras-chave identificadas.

Exemplos ilustrativos:

- JavaScript.
- React.
- SQL.
- Git.
- Análise de dados.

Os termos exibidos devem vir da análise real, e não de uma lista fixa.

### 9.4. Palavras-chave ausentes

Título:

**O que pode estar faltando**

Exibir badges de atenção com os requisitos não identificados.

Para cada termo ausente, explicar:

- Por que ele aparece na vaga.
- Qual sua relevância.
- Se existe alguma experiência fornecida pelo candidato que possa demonstrar uma competência equivalente.
- Se é necessário adquirir aquela habilidade ou apenas melhorar a descrição de uma experiência existente.

Não inserir essas palavras automaticamente no currículo como se fossem competências comprovadas.

### 9.5. Pontos fortes

Exibir os aspectos do currículo que mais se alinham com a vaga.

Apresentar frases objetivas e específicas.

### 9.6. Oportunidades de melhoria

Mostrar oportunidades como:

- Melhorar a descrição das atividades realizadas.
- Destacar tecnologias já utilizadas.
- Reorganizar a seção de competências.
- Explicitar resultados comprovados.
- Dar maior visibilidade a projetos relevantes.
- Melhorar o resumo profissional.

As recomendações devem ser fundamentadas nos dados fornecidos pelo usuário.

### 9.7. Ações disponíveis

Disponibilizar os seguintes botões:

- **Gerar currículo otimizado**
- Ver detalhes da análise.
- Copiar resumo.
- Salvar análise.
- Voltar ao dashboard.

As análises devem ser salvas automaticamente quando processadas com sucesso, evitando duplicação caso o usuário apenas atualize a página.

---

## 10. Gerador de currículo ATS Friendly

Implementar o gerador de currículos como uma das funcionalidades centrais da aplicação.

Ao clicar em **Gerar currículo otimizado**, a IA deverá produzir uma versão aprimorada do currículo com base:

1. No currículo original.
2. Na descrição da vaga.
3. Nas palavras-chave encontradas.
4. Nos requisitos identificados.
5. No nicho profissional selecionado.
6. Nas recomendações da análise.

### 10.1. Regras obrigatórias de geração

A IA deverá:

- Preservar empresas, cargos e datas originais.
- Preservar a formação acadêmica.
- Preservar cursos e certificações informados.
- Preservar as tecnologias efetivamente mencionadas.
- Melhorar clareza e objetividade.
- Corrigir erros gramaticais.
- Reduzir repetições desnecessárias.
- Reorganizar as informações.
- Destacar experiências relevantes para a vaga.
- Utilizar palavras-chave somente quando sustentadas pelo currículo original.
- Evitar linguagem exagerada ou declarações sem evidências.

**Proibição absoluta:** criar experiências profissionais fictícias, inventar resultados numéricos, acrescentar certificações inexistentes ou afirmar domínio de tecnologias não mencionadas ou comprovadas pelo candidato.

Se uma palavra-chave importante estiver ausente, apresentar a sugestão separadamente, sem inseri-la como competência adquirida.

Se uma informação necessária estiver ausente, não preenchê-la por dedução. Omitir o campo ou solicitar que o usuário forneça a informação.

### 10.2. Estrutura do currículo gerado

Utilizar uma estrutura profissional e compatível com padrões ATS:

**NOME COMPLETO**

Cidade e estado, telefone, e-mail e LinkedIn, somente quando fornecidos pelo usuário.

### RESUMO PROFISSIONAL

Apresentação breve e objetiva, destacando as experiências, competências e qualificações comprovadas mais relevantes para a vaga.

### COMPETÊNCIAS

Organização das competências e tecnologias efetivamente identificadas no currículo.

### EXPERIÊNCIA PROFISSIONAL

Para cada experiência:

- Cargo.
- Empresa.
- Período.
- Atividades desempenhadas.
- Resultados informados pelo candidato.

Melhorar a redação sem alterar os fatos.

### PROJETOS

Quando houver projetos informados, destacar aqueles mais relacionados à vaga.

### FORMAÇÃO ACADÊMICA

Instituição, curso e período, conforme as informações fornecidas.

### CURSOS E CERTIFICAÇÕES

Listar somente qualificações reais que constem no currículo original.

### IDIOMAS

Incluir somente os idiomas e níveis informados pelo usuário.

Não obrigar o candidato a preencher todas as seções. Omitir seções sem informações disponíveis.

### 10.3. Padrões de formatação ATS

O documento deve utilizar:

- Layout de uma coluna.
- Títulos convencionais.
- Texto selecionável.
- Fonte profissional e legível.
- Hierarquia clara entre títulos e seções.
- Datas em formato consistente.
- Marcadores simples.
- Margens adequadas.
- Estrutura linear.

Evitar:

- Tabelas complexas.
- Colunas múltiplas.
- Gráficos de habilidades.
- Barras de proficiência.
- Ícones decorativos.
- Imagens.
- Fotografias.
- Caixas de texto complexas.
- Elementos que possam prejudicar a extração automática de informações.

A interface da aplicação pode ser visualmente vibrante. Entretanto, o documento final deverá ser sóbrio, profissional e otimizado para leitura automatizada.

---

## 11. Editor do currículo otimizado

Após a geração, apresentar uma área de edição.

Dividir a tela em duas áreas ou utilizar abas:

**Visualização do currículo**

Exibir como o documento ficará após a exportação.

**Editor**

Permitir que o usuário ajuste o conteúdo antes de exportar.

Funcionalidades:

- Editar texto.
- Corrigir informações.
- Alterar títulos.
- Remover informações.
- Reorganizar seções.
- Salvar alterações.
- Restaurar uma versão anterior.
- Copiar o currículo completo.

O usuário deve ter controle sobre o conteúdo final.

Exibir a mensagem:

**Revise seu currículo antes de enviá-lo.**

As informações geradas pela IA devem ser conferidas pelo usuário para garantir que estejam corretas.

---

## 12. Exportação em Word (.docx)

Implementar exportação real utilizando a biblioteca `docx`.

Criar botão principal:

**Baixar currículo em Word (.docx)**

O arquivo deverá:

- Ser válido e abrir no Microsoft Word.
- Ser compatível com editores como LibreOffice e Google Docs.
- Preservar acentuação e caracteres especiais.
- Utilizar títulos e subtítulos adequados.
- Possuir layout de uma coluna.
- Utilizar estilos de parágrafo consistentes.
- Preservar a organização das seções.
- Evitar elementos gráficos complexos.
- Permitir edição posterior pelo usuário.

O conteúdo exportado deve corresponder exatamente à última versão salva no editor.

Nome sugerido para o arquivo:

`Curriculo_NomeDoCandidato_Vaga.docx`

Caso o nome não esteja disponível, utilizar um nome genérico.

Além do DOCX, permitir:

- Copiar o conteúdo em texto.
- Visualizar a versão final antes do download.

Não considerar a exportação concluída até que o arquivo seja efetivamente gerado e disponibilizado para download.

---

## 13. Histórico de análises

Criar uma página chamada **Histórico de análises**.

Exibir todas as análises realizadas pelo usuário.

### Informações da tabela

- Cargo.
- Empresa.
- Data.
- Nicho.
- Currículo utilizado.
- Número da versão.
- Percentual de match.
- Situação.

### Funcionalidades

- Abrir uma análise anterior.
- Visualizar palavras-chave.
- Consultar recomendações.
- Visualizar versões do currículo.
- Comparar versões.
- Reutilizar uma descrição de vaga.
- Excluir uma análise, com confirmação.
- Pesquisar por cargo ou empresa.
- Filtrar por data ou nicho.

Cada usuário deve acessar exclusivamente seu próprio histórico.

---

## 14. Evolução do match entre versões

Criar uma funcionalidade específica para acompanhar a evolução do currículo.

O objetivo é demonstrar como as alterações realizadas influenciam a compatibilidade com uma mesma vaga.

### Funcionamento

1. O candidato realiza a primeira análise.
2. O sistema registra a versão original do currículo e sua pontuação.
3. O usuário gera uma versão otimizada.
4. O usuário pode editar o documento.
5. O sistema salva a nova versão.
6. O usuário solicita uma nova análise utilizando a mesma descrição de vaga.
7. O sistema registra a nova pontuação.
8. O dashboard atualiza o gráfico de evolução.

### Exemplo ilustrativo

| Versão | Match |
|---|---:|
| Currículo original | 48% |
| Primeira otimização | 67% |
| Segunda revisão | 81% |

Os valores acima são apenas exemplos de apresentação. O sistema deverá utilizar as pontuações efetivamente calculadas.

### Comparação entre versões

Criar uma visualização que apresente:

- Percentual anterior.
- Percentual atual.
- Diferença em pontos percentuais.
- Palavras-chave adicionadas ao currículo.
- Requisitos que passaram a ser atendidos.
- Melhorias na apresentação profissional.

Não aumentar artificialmente a pontuação apenas porque o texto foi reescrito.

Uma nova versão somente deverá receber uma nova pontuação após passar pelo mesmo processo de análise e pelos mesmos critérios aplicáveis à vaga.

Permitir acompanhar diferentes oportunidades sem misturar suas pontuações.

---

## 15. Especialização por nicho profissional

O MatchCV deverá oferecer análises contextualizadas conforme a área de atuação.

### 15.1. Tecnologia

Ao selecionar Tecnologia, a IA deverá reconhecer terminologias e competências relacionadas a:

- Desenvolvimento Front-end.
- Desenvolvimento Back-end.
- Desenvolvimento Full Stack.
- Desenvolvimento Mobile.
- Banco de dados.
- Engenharia de software.
- Cloud Computing.
- DevOps.
- Cibersegurança.
- Redes de computadores.
- Análise de dados.
- Inteligência artificial.
- Testes de software.
- Automação.

Reconhecer ferramentas, linguagens, frameworks e tecnologias mencionadas na vaga e no currículo.

Exemplos de termos que podem ser identificados, conforme o conteúdo real:

- JavaScript.
- TypeScript.
- Python.
- Java.
- C++.
- React.
- Node.js.
- PostgreSQL.
- MySQL.
- Docker.
- Git.
- AWS.
- Linux.
- APIs REST.
- CI/CD.

As tecnologias acima são referências de análise, não competências a serem atribuídas automaticamente ao candidato.

Para vagas de tecnologia, dar atenção especial a:

- Projetos desenvolvidos.
- Repositórios e portfólio, quando informados.
- Linguagens utilizadas.
- Frameworks.
- Ferramentas.
- Arquitetura.
- Experiências práticas.
- Competências técnicas demonstradas.

### 15.2. Primeiro emprego

Ao selecionar Primeiro Emprego, adaptar a lógica de análise para pessoas com pouca ou nenhuma experiência profissional formal.

Considerar:

- Formação acadêmica.
- Cursos livres.
- Certificações.
- Projetos acadêmicos.
- Projetos pessoais.
- Trabalho voluntário.
- Atividades extracurriculares.
- Conhecimentos técnicos.
- Competências transferíveis.
- Participação em atividades práticas.

Não penalizar automaticamente a ausência de experiência formal.

A IA poderá recomendar como apresentar projetos acadêmicos e experiências práticas, desde que tenham sido fornecidos pelo candidato.

### 15.3. Outros nichos

Manter arquitetura extensível para adicionar novas especializações no futuro.

A especialização não deve criar barreiras entre os usuários nem exigir que todos escolham um nicho específico.

---

## 16. Estrutura do banco de dados

Utilizar Supabase PostgreSQL.

Criar tabelas normalizadas, relacionamentos e índices adequados.

### 16.1. Tabela `profiles`

Armazenar informações complementares do usuário.

Campos:

- `id`: UUID, referência ao usuário autenticado.
- `full_name`: nome completo.
- `email`: e-mail.
- `preferred_niche`: nicho preferido.
- `created_at`: data de criação.
- `updated_at`: última atualização.

### 16.2. Tabela `resumes`

Armazenar os currículos principais.

Campos:

- `id`: UUID.
- `user_id`: referência ao proprietário.
- `title`: nome do currículo.
- `created_at`.
- `updated_at`.

### 16.3. Tabela `resume_versions`

Armazenar as diferentes versões dos currículos.

Campos:

- `id`: UUID.
- `resume_id`: referência ao currículo.
- `user_id`: proprietário.
- `version_number`: número da versão.
- `content`: conteúdo integral do currículo.
- `source_type`: original, otimizado ou editado.
- `created_at`.

Cada versão deverá permanecer preservada para possibilitar comparações e recuperação de versões anteriores.

### 16.4. Tabela `opportunities`

Armazenar as oportunidades analisadas.

Campos:

- `id`: UUID.
- `user_id`: proprietário.
- `job_title`: cargo.
- `company_name`: empresa, opcional.
- `job_description`: descrição integral da vaga.
- `niche`: nicho selecionado.
- `created_at`.
- `updated_at`.

### 16.5. Tabela `analyses`

Armazenar os resultados de cada análise.

Campos:

- `id`: UUID.
- `user_id`: proprietário.
- `opportunity_id`: referência à oportunidade.
- `resume_id`: referência ao currículo.
- `resume_version_id`: versão efetivamente analisada.
- `match_score`: percentual geral.
- `score_breakdown`: pontuação detalhada em JSONB.
- `keywords_found`: palavras-chave identificadas em JSONB.
- `keywords_missing`: palavras-chave ausentes em JSONB.
- `partial_matches`: correspondências parciais em JSONB.
- `strengths`: pontos fortes em JSONB.
- `gaps`: lacunas identificadas em JSONB.
- `recommendations`: recomendações em JSONB.
- `summary`: resumo da análise.
- `created_at`.

Criar índices para consultas por usuário, oportunidade, currículo e data.

### 16.6. Segurança e RLS

Ativar Row Level Security em todas as tabelas que armazenam dados privados.

Implementar políticas que garantam:

- Usuários só podem consultar seus próprios dados.
- Usuários só podem cadastrar dados vinculados à própria conta.
- Usuários só podem editar registros de sua propriedade.
- Usuários não podem excluir registros de outros usuários.
- Relações entre tabelas devem validar a propriedade dos registros.

Não confiar somente na validação do front-end.

Validar a identidade e as permissões do usuário no servidor.

Criar migrations SQL organizadas e documentadas.

---

## 17. Segurança, privacidade e conformidade com a LGPD

Como a aplicação manipula currículos, dados de contato e informações profissionais, implementar medidas de proteção desde o início.

### Requisitos

- HTTPS.
- Autenticação segura.
- Controle de sessão.
- Row Level Security.
- Proteção das chaves de API.
- Validação de entradas.
- Tratamento de erros.
- Prevenção contra acesso indevido.
- Proteção contra consultas não autorizadas.
- Exclusão segura de dados.
- Política de privacidade.
- Termos de uso.
- Consentimento informado para processamento por IA.

### Privacidade

Explicar ao usuário:

- Quais dados são armazenados.
- Para que os dados são utilizados.
- Como ocorre o processamento por IA.
- Quais serviços externos recebem informações para processamento.
- Como solicitar exclusão dos dados.
- Por quanto tempo os dados serão mantidos.

Não registrar currículos completos ou descrições de vagas em logs desnecessários.

Não utilizar dados de candidatos para treinamento de modelos sem consentimento específico e fundamento adequado.

Permitir que o usuário solicite a exclusão de sua conta e dos dados associados, observadas as obrigações legais aplicáveis.

A implementação deverá respeitar os princípios e requisitos da LGPD.

---

## 18. SEO — Search Engine Optimization

Preparar a landing page e as páginas públicas para mecanismos de busca tradicionais.

### Requisitos técnicos

- Título personalizado por página.
- Meta description.
- URLs amigáveis.
- Hierarquia correta de H1, H2 e H3.
- HTML semântico.
- Sitemap XML.
- Robots.txt.
- Canonical URLs.
- Open Graph.
- Twitter Cards.
- Imagens otimizadas.
- Descrições alternativas para imagens.
- Performance otimizada.
- Carregamento rápido.
- Responsividade.
- Links internos.

### Palavras-chave estratégicas

Trabalhar naturalmente termos como:

- Analisador de currículo.
- Análise de currículo com inteligência artificial.
- Comparar currículo com vaga.
- Currículo ATS.
- Otimizar currículo para ATS.
- Palavras-chave para currículo.
- Criar currículo profissional.
- Currículo para primeiro emprego.
- Currículo para vagas de tecnologia.
- Análise de compatibilidade profissional.

Não utilizar repetição artificial de palavras-chave.

### Conteúdo público

Criar conteúdo informativo na landing page para explicar:

- O que é ATS.
- Como funcionam os filtros de currículos.
- Como adaptar um currículo para uma vaga.
- Como melhorar um currículo de tecnologia.
- Como elaborar um currículo para primeiro emprego.

As páginas devem entregar informações úteis e originais.

---

## 19. GEO — Generative Engine Optimization

Preparar a presença pública do MatchCV para melhorar sua compreensão e possibilidade de citação por mecanismos de busca baseados em inteligência artificial.

Implementar:

### Dados estruturados

Utilizar JSON-LD adequado ao conteúdo real das páginas.

Avaliar a implementação de:

- `Organization`.
- `SoftwareApplication`.
- `WebSite`.
- `FAQPage`, quando o conteúdo visível atender aos requisitos aplicáveis.

Os dados estruturados devem corresponder ao conteúdo efetivamente apresentado na página.

### Conteúdo semântico

Desenvolver textos claros e objetivos, com:

- Definições diretas.
- Perguntas e respostas.
- Explicações práticas.
- Conceitos organizados.
- Seções com títulos descritivos.
- Informações consistentes sobre o produto.

### Autoridade e compreensão

Apresentar de forma clara:

- O que é o MatchCV.
- Para quem a plataforma foi criada.
- Como funciona a análise de compatibilidade.
- O que significa a pontuação.
- Como funciona a otimização ATS.
- Quais são os limites da ferramenta.
- Como os dados dos usuários são protegidos.

Criar informações institucionais consistentes para facilitar a identificação da aplicação por mecanismos de busca e sistemas de IA.

Não afirmar que GEO garante citações ou posicionamento em respostas de inteligência artificial.

---

## 20. Experiência do usuário e estados da aplicação

Garantir que todos os componentes tenham estados funcionais.

### Estados de carregamento

Utilizar Skeletons e indicadores durante:

- Carregamento do dashboard.
- Consulta ao histórico.
- Processamento da análise.
- Geração do currículo.
- Salvamento de versões.
- Exportação do DOCX.

### Estados vazios

Criar mensagens claras quando:

- Não houver análises.
- Não houver currículos cadastrados.
- Não houver histórico.
- Não existirem versões anteriores.
- Não houver dados suficientes para exibir gráficos.

### Estados de erro

Apresentar mensagens compreensíveis para:

- Falha de autenticação.
- E-mail não confirmado.
- Erro de conexão.
- Falha na API de IA.
- Resposta inválida da IA.
- Falha no salvamento.
- Falha na exportação.

Permitir tentar novamente quando apropriado.

### Confirmações

Solicitar confirmação antes de:

- Excluir uma análise.
- Excluir um currículo.
- Remover uma versão.
- Excluir a conta.

Não utilizar alertas genéricos do navegador quando houver componentes adequados do Shadcn/ui.

---

## 21. Requisitos de acessibilidade e responsividade

Seguir boas práticas de acessibilidade.

- Contraste adequado.
- Navegação por teclado.
- Labels associados aos campos.
- Foco visível.
- Textos alternativos.
- Mensagens de erro acessíveis.
- Componentes compatíveis com leitores de tela.
- Botões com nomes claros.
- Não depender somente de cores.
- Respeitar a preferência por redução de movimento.

A aplicação deverá funcionar corretamente em:

- Desktop.
- Notebook.
- Tablet.
- Smartphone.

No celular, reorganizar gráficos, tabelas e formulários sem prejudicar a experiência.

---

## 22. Organização do código

Manter o código organizado por funcionalidades.

Estrutura sugerida:

```text
src/
├── components/
│   ├── ui/
│   ├── layout/
│   ├── dashboard/
│   ├── analysis/
│   ├── resume/
│   └── common/
│
├── pages/
│   ├── LandingPage.tsx
│   ├── LoginPage.tsx
│   ├── RegisterPage.tsx
│   ├── DashboardPage.tsx
│   ├── NewAnalysisPage.tsx
│   ├── AnalysisResultPage.tsx
│   ├── ResumeEditorPage.tsx
│   ├── HistoryPage.tsx
│   ├── EvolutionPage.tsx
│   └── SettingsPage.tsx
│
├── hooks/
├── contexts/
├── services/
├── integrations/
│   └── supabase/
├── schemas/
├── types/
├── utils/
└── styles/
```

Estruturar as Supabase Edge Functions para:

```text
supabase/
└── functions/
    ├── analyze-resume/
    ├── generate-resume/
    └── send-notification/
```

Adequar os nomes e responsabilidades caso a implementação exija funções adicionais.

Utilizar tipagem TypeScript consistente.

Evitar:

- Componentes gigantes.
- Regras de negócio dentro de componentes visuais.
- Código duplicado.
- Consultas diretas e desorganizadas ao banco.
- Chaves privadas no cliente.
- Dados simulados em funcionalidades que deveriam consultar o banco real.

---

## 23. Fluxo completo da aplicação

Implementar o seguinte fluxo de ponta a ponta:

```text
USUÁRIO
   |
   v
LANDING PAGE
   |
   v
CADASTRO / LOGIN
   |
   v
CONFIRMAÇÃO DE E-MAIL
   |
   v
DASHBOARD
   |
   v
NOVA ANÁLISE
   |
   v
SELEÇÃO DO NICHO
   |
   v
DESCRIÇÃO DA VAGA
   |
   v
CURRÍCULO ORIGINAL
   |
   v
VALIDAÇÃO DOS DADOS
   |
   v
ANÁLISE POR IA
   |
   v
CÁLCULO DO MATCH
   |
   v
RESULTADO DA ANÁLISE
   |
   v
PALAVRAS-CHAVE E RECOMENDAÇÕES
   |
   v
GERAÇÃO DO CURRÍCULO ATS
   |
   v
EDITOR DE CURRÍCULO
   |
   v
SALVAR NOVA VERSÃO
   |
   v
EXPORTAR DOCX
   |
   v
REANALISAR CURRÍCULO
   |
   v
ATUALIZAR EVOLUÇÃO DO MATCH
```

Cada etapa deve funcionar com dados reais e persistência no banco.

O usuário deverá conseguir sair da aplicação e retornar posteriormente sem perder suas análises e versões salvas.

---

## 24. Critérios de aceitação e testes

Antes de considerar o projeto concluído, testar os seguintes cenários:

### Autenticação

- [ ] Cadastrar um novo usuário.
- [ ] Enviar confirmação por e-mail via Resend.
- [ ] Confirmar o e-mail.
- [ ] Realizar login.
- [ ] Recuperar senha.
- [ ] Encerrar sessão.
- [ ] Bloquear páginas privadas para usuários não autenticados.

### Análise

- [ ] Inserir uma descrição de vaga.
- [ ] Inserir um currículo.
- [ ] Validar campos obrigatórios.
- [ ] Selecionar nicho profissional.
- [ ] Executar análise real por IA.
- [ ] Calcular pontuação.
- [ ] Exibir palavras-chave encontradas.
- [ ] Exibir palavras-chave ausentes.
- [ ] Exibir pontos fortes e oportunidades de melhoria.
- [ ] Tratar erros da API de IA.

### Otimização

- [ ] Gerar currículo otimizado.
- [ ] Preservar as informações originais.
- [ ] Não inventar competências.
- [ ] Não inventar experiências.
- [ ] Permitir edição.
- [ ] Salvar nova versão.
- [ ] Recuperar uma versão anterior.
- [ ] Exportar arquivo DOCX válido.
- [ ] Conferir o conteúdo exportado.

### Banco de dados

- [ ] Salvar usuários e perfis.
- [ ] Salvar currículos.
- [ ] Salvar versões.
- [ ] Salvar oportunidades.
- [ ] Salvar análises.
- [ ] Consultar histórico.
- [ ] Validar políticas RLS.
- [ ] Impedir acesso cruzado entre usuários.

### Dashboard

- [ ] Exibir indicadores reais.
- [ ] Exibir análises recentes.
- [ ] Exibir gráfico de evolução.
- [ ] Comparar versões da mesma oportunidade.
- [ ] Atualizar os indicadores após novas análises.

### SEO e GEO

- [ ] Verificar metadados.
- [ ] Verificar sitemap.
- [ ] Verificar robots.txt.
- [ ] Verificar URLs canônicas.
- [ ] Verificar dados estruturados.
- [ ] Verificar indexação das páginas públicas.
- [ ] Garantir que páginas privadas não sejam indexadas.

---

## 25. Prioridade de implementação

Desenvolva o produto por etapas, mas mantenha a arquitetura preparada para todas as funcionalidades especificadas.

### Prioridade 1 — MVP funcional

Implementar primeiro:

1. Landing page.
2. Cadastro e login.
3. Confirmação de e-mail com Resend.
4. Dashboard básico.
5. Formulário de análise.
6. Processamento real por IA.
7. Cálculo e apresentação do match.
8. Identificação de palavras-chave.
9. Geração de currículo otimizado.
10. Editor.
11. Exportação DOCX.
12. Salvamento das análises e versões.

### Prioridade 2 — Evolução e especialização

Implementar:

1. Histórico completo.
2. Comparação entre versões.
3. Dashboard de evolução.
4. Especialização em Tecnologia.
5. Especialização em Primeiro Emprego.
6. Filtros e pesquisa.
7. Configurações do perfil.

### Prioridade 3 — Descoberta e crescimento

Implementar:

1. SEO técnico.
2. GEO.
3. Conteúdo institucional.
4. FAQ.
5. Dados estruturados.
6. Otimizações de performance.
7. Melhorias de acessibilidade.

---

## 26. Instruções finais para o Lovable

Desenvolva o MatchCV como um produto SaaS real, com aparência profissional e experiência de uso de alta qualidade.

Siga rigorosamente as seguintes orientações:

1. Utilize Shadcn/ui como base do design system e Tailwind CSS para estilização.
2. Utilize a paleta de cores definida, com destaque para violeta, ciano, verde e cores de atenção.
3. Priorize uma interface intuitiva, responsiva e visualmente organizada.
4. Não crie funcionalidades apenas decorativas: todos os botões, formulários, menus e ações devem funcionar.
5. Utilize Supabase para autenticação e persistência dos dados.
6. Configure a confirmação de e-mail com Resend de maneira segura.
7. Faça todas as operações sensíveis no servidor.
8. Utilize inteligência artificial para a análise e otimização dos currículos.
9. Valide as respostas geradas pela IA antes de utilizá-las.
10. Implemente a exportação real para DOCX.
11. Salve todas as análises e versões dos currículos.
12. Utilize dados reais do banco nos gráficos e indicadores.
13. Implemente proteção RLS em todas as tabelas privadas.
14. Não invente experiências, competências ou qualificações para os candidatos.
15. Não utilize dados fictícios como se fossem resultados reais.
16. Não considere integrações concluídas sem que estejam efetivamente configuradas e testadas.
17. Não comprometa a estrutura ATS do arquivo exportado para priorizar efeitos visuais.
18. Preserve a integridade das informações originais do usuário.
19. Documente configurações externas e variáveis de ambiente necessárias.
20. Teste o fluxo completo antes de finalizar.

**Diretriz principal:** a primeira entrega deve ser um fluxo funcional de ponta a ponta: cadastro, confirmação de e-mail, inserção do currículo e da vaga, análise de compatibilidade, identificação de palavras-chave, geração do currículo otimizado, edição, exportação DOCX e salvamento no histórico.

Não priorize funcionalidades secundárias em detrimento desse fluxo.

O resultado esperado é uma plataforma SaaS funcional, visualmente moderna, segura e preparada para evoluir, que ajude candidatos a apresentar suas qualificações de maneira mais estratégica e aumentar a qualidade do alinhamento entre seus currículos e as vagas desejadas.

**Nome do produto:** MatchCV  
**Slogan:** Seu talento merece ser encontrado.  
**Proposta de valor:** Compare, otimize e evolua seu currículo com inteligência artificial — sem inventar sua trajetória.
