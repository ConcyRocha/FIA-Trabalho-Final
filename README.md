# FIA-Trabalho-Final
# Raciocínio Espacial Neuro-Simbólico com LTNtorch

Este repositório contém o Trabalho Final da disciplina de **Fundamentos de Inteligência Artificial **, focado na construção de um agente neuro-simbólico utilizando **Logic Tensor Networks (LTN)**.

## 👥 Equipe
* **André Kaled Duarte Coutinho Andrade** (andre.andrade@icomp.ufam.edu.br)
* **Conceição Barbosa Rocha** (conceicao.rocha@icomp.ufam.edu.br)
* **Julia Evelyn Chaparro Ferreira** (julia.ferreira@icomp.ufam.edu.br)
* **Luiz Henrique Barbosa Costa** (luiz.costa@icomp.ufam.edu.br)
* **Marcus Phablo Pereira de Oliveira** (marcus.oliveira@icomp.ufam.edu.br)
* **Paulo Victor Fernandes de Melo** (paulo.fernandes@icomp.ufam.edu.br)
* **Sven Maximilian Kalisch** (sven.kalisch@icomp.ufam.edu.br)

---

## 📝 Sobre o Projeto

O objetivo deste trabalho é desenvolver um agente capaz de entender relações espaciais em um ambiente 2D simplificado (estilo CLEVR), utilizando **vetores de características** em vez de processamento de imagens brutas. O projeto utiliza LTN para ensinar à rede regras lógicas sobre como os objetos se relacionam entre si.

### Estrutura dos Dados
Os objetos são representados por um vetor de características de tamanho 11:
* **[0-1]:** Posição (x, y) normalizada.
* **[2-4]:** Cores (One-Hot: Vermelho, Verde, Azul).
* **[5-9]:** Formas (One-Hot: Círculo, Quadrado, Cilindro, Cone, Triângulo).
* **[10]:** Tamanho (Pequeno/Grande).

## 🚀 Funcionalidades e Tarefas

O desenvolvimento foi dividido em quatro tarefas principais de raciocínio lógico:

### 1. Taxonomia e Formas
Definição de predicados base para classificação de objetos (`isCylinder`, `isCone`, `isSmall`, etc.) e aplicação de axiomas de unicidade e completude.

### 2. Raciocínio Espacial (Horizontal)
Implementação de relações de posição relativa:
* **Predicados:** `leftOf`, `rightOf`, `closeTo` (Kernel Gaussiano), `inBetween`.
* **Axiomas:** Irreflexividade, Assimetria, Inverso e Transitividade.
* **Consultas:** Identificação de objetos extremos (`lastOnTheLeft`, `lastOnTheRight`).

### 3. Raciocínio Vertical
Extensão para o eixo vertical com predicados `below`, `above` e regras de empilhamento (`canStack`), onde cones e triângulos não podem servir de base.

### 4. Raciocínio Composto
Resolução de queries complexas que exigem filtragem composta e dedução, como:
> "Existe algum objeto Pequeno que esteja Abaixo de um Cilindro E à Esquerda de um Quadrado?"

## 📊 Métricas e Resultados

O projeto avalia a performance do modelo neuro-simbólico através de 5 execuções em datasets aleatórios distintos, reportando:
* Satisfatibilidade (satAgg)
* Acurácia
* Precisão
* Recall
* F1 Score

## 🛠️ Tecnologias Utilizadas
* Python
* PyTorch
* LTNtorch (Logic Tensor Networks)

---
*Universidade Federal do Amazonas (UFAM) - Instituto de Computação (IComp)*
*Professor: Edjard Mota - Novembro 2025*
