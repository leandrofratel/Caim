# 00 - Definição do Problema

# CAIM — Contextual Analysis and Inferential Modeling

## Visão Geral

O CAIM é um sistema de inferência narrativa capaz de transformar documentos não estruturados ou desorganizados em uma representação estruturada do conhecimento, preservando entidades, eventos, relações e evidências utilizadas durante o processo de inferência.

O projeto utiliza como estudo de caso o livro **Mandíbula de Caim**, cuja narrativa está distribuída em 100 páginas embaralhadas. Entretanto, o objetivo do projeto não é resolver apenas esse livro, mas desenvolver uma arquitetura capaz de reconstruir narrativas fragmentadas em qualquer conjunto de documentos.

---

# Objetivo Geral

Construir um sistema capaz de inferir conhecimento a partir de documentos desorganizados e convertê-lo em uma representação estruturada da narrativa.

A ordenação das páginas é uma consequência da reconstrução da narrativa e não o objetivo principal do sistema.

---

# Objetivos Específicos

O sistema deverá ser capaz de:

* Extrair conhecimento de documentos textuais.
* Identificar entidades relevantes.
* Detectar eventos narrativos.
* Construir relações entre entidades.
* Inferir conexões implícitas.
* Reconstruir a sequência lógica da narrativa.
* Ordenar páginas com base na narrativa reconstruída.
* Responder perguntas sobre o documento.
* Explicar quais evidências sustentam cada inferência realizada.

---

# Problema

Os limites físicos de um documento não representam os limites da narrativa.

Uma página pode:

* iniciar um diálogo;
* terminar outro;
* conter parte de um poema;
* apresentar personagens sem contexto;
* descrever consequências de eventos ocorridos anteriormente;
* fazer referência a acontecimentos futuros.

Da mesma forma, um único evento pode ocupar diversas páginas consecutivas ou até páginas muito distantes entre si.

Portanto, utilizar a página como unidade de conhecimento produz uma representação inadequada da narrativa.

---

# Hipótese Central

A narrativa pode ser reconstruída independentemente da organização física do documento.

Ao identificar entidades, eventos, estados e relações presentes nos fragmentos narrativos, torna-se possível inferir uma sequência lógica dos acontecimentos e, posteriormente, reconstruir a ordem física das páginas.

---

# Princípio Fundamental

## Princípio da Independência entre Estrutura Física e Estrutura Semântica

O conhecimento nunca deve depender da organização física do documento.

As páginas representam apenas uma estrutura de armazenamento.

A narrativa representa a estrutura semântica do conhecimento.

O sistema sempre deve reconstruir a narrativa antes de reconstruir as páginas.

---

# Modelo Conceitual

O CAIM organiza o conhecimento em diferentes níveis de abstração.

```text
Documento

↓

Estrutura Física

↓

Fragmentos Narrativos

↓

Modelo Narrativo

↓

Grafo de Conhecimento

↓

Inferência

↓

Narrativa Reconstruída

↓

Reconstrução Física das Páginas
```

---

# Camadas do Sistema

## 1. Estrutura Física

Representa apenas a organização física do documento.

Contém:

* Documento
* Página
* Texto bruto
* Parágrafos
* Metadados

Essa camada não realiza inferências.

---

## 2. Fragmentos Narrativos

Representam unidades coerentes da narrativa.

Um fragmento pode corresponder a:

* parte de um diálogo;
* parte de um poema;
* descrição de um ambiente;
* trecho de um evento;
* carta;
* pensamento;
* narrativa em primeira pessoa;
* lembrança.

Os fragmentos não respeitam necessariamente os limites das páginas.

Uma página pode conter vários fragmentos.

Um fragmento pode ocupar várias páginas.

---

## 3. Modelo Narrativo

Cada fragmento gera uma representação estruturada contendo:

### Entidades

* Personagens
* Lugares
* Objetos
* Expressões temporais

### Eventos

Eventos narrativos identificados no texto.

### Relações

Relacionamentos entre entidades.

Exemplos:

* conhece
* matou
* entregou
* encontrou
* pertence a

### Estados

Representam alterações ao longo da narrativa.

Exemplos:

* vivo
* morto
* desaparecido
* preso
* ferido

### Diálogos

Conversas entre personagens.

### Emoções

Estados emocionais explícitos ou inferidos.

### Referências

Referências internas da narrativa.

Exemplos:

* ele
* ela
* novamente
* anteriormente
* como vimos

### Evidências

Trechos do documento utilizados para justificar cada informação extraída.

Cada inferência realizada pelo sistema deve ser acompanhada de suas evidências.

---

## 4. Grafo de Conhecimento

Todo o conhecimento extraído é convertido em um grafo.

Os nós representam entidades, eventos, estados, locais, objetos e demais elementos narrativos.

As arestas representam relações e dependências entre esses elementos.

O grafo constitui a representação principal do conhecimento produzido pelo sistema.

---

## 5. Motor de Inferência

Responsável por descobrir relações que não estão explicitamente presentes no texto.

Exemplos:

* continuidade de diálogos;
* continuidade de poemas;
* continuidade de eventos;
* evolução temporal;
* mudanças de estado;
* ligações entre personagens;
* conexões entre fragmentos narrativos.

Cada inferência deve possuir um nível de confiança e evidências associadas.

---

## 6. Reconstrução da Narrativa

A partir do grafo de conhecimento, o sistema reconstrói uma sequência lógica dos acontecimentos.

Essa sequência representa a narrativa inferida pelo sistema.

Ela independe completamente da organização física das páginas.

---

## 7. Reconstrução Física

Somente após reconstruir a narrativa o sistema tenta determinar a ordem das páginas.

As páginas passam a ser vistas como recipientes físicos que armazenam fragmentos da narrativa.

---

## 8. Consulta

Como consequência da estrutura criada, o sistema poderá responder perguntas como:

* Quem são os personagens?
* Quem são as vítimas?
* Quem são os assassinos?
* Onde determinado personagem aparece?
* Quais objetos estão relacionados a determinado evento?
* Quantos eventos existem?
* Qual personagem possui maior centralidade?
* Quais páginas possuem maior probabilidade de serem consecutivas?

---

# Fluxo Conceitual do Sistema

```text
Documento (PDF)

        │

        ▼

Extração do Texto

        │

        ▼

Fragmentação da Narrativa

        │

        ▼

Construção do Modelo Narrativo

        │

        ▼

Grafo de Conhecimento

        │

        ▼

Motor de Inferência

        │

        ▼

Reconstrução da Narrativa

        │

        ▼

Reconstrução das Páginas

        │

        ▼

Consultas e Sistema de Perguntas
```

---

# Filosofia do Projeto

O CAIM não organiza páginas.

O CAIM reconstrói conhecimento.

A ordem correta das páginas é apenas uma consequência da reconstrução da narrativa.

Toda inferência realizada pelo sistema deve ser explicável, justificável e baseada em evidências presentes no documento.

Essa filosofia orienta todas as decisões arquiteturais do projeto.
