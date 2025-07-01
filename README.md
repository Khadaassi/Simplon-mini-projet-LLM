# Simplon - Mini Projet LLM : Assistant IA pour une pizzeria

## Contexte

En tant que développeur Intelligence Artificielle / Ingénieur IA Full-Stack, ce projet d’une journée avait pour objectif de développer un assistant conversationnel pour la pizzeria *Bella Napoli*. Celle-ci reçoit de nombreux appels concernant :

* les ingrédients de ses pizzas,
* les allergènes,
* les préférences alimentaires (halal, végétarien, etc.).

Le personnel étant saturé par ces demandes, cela nuit à la qualité de service et au volume de commandes.

### Objectif technique

Développer un assistant IA basé sur une architecture RAG (Retrieval-Augmented Generation) avec LangChain, interrogeant une base documentaire PDF fournie (menus, compositions, allergènes…).
Le modèle LLM utilisé est Mistral, exécuté localement via Ollama.
Une interface utilisateur avec Gradio était prévue mais finalement non obligatoire.

---

## Architecture technique

### Pipeline RAG

1. Prétraitement PDF avec extraction du contenu textuel
2. Vectorisation avec embeddings
3. Indexation FAISS
4. Interrogation contextuelle avec LangChain
5. Génération de réponse par LLM (Mistral via Ollama)

### Scripts principaux

* `rag_simple.py` : initialise le vecteur store et les embeddings (à lancer en premier)
* `rag_langchain.py` : lance l’agent conversationnel

---

## Technologies utilisées

| Outil / Lib      | Rôle                               |
| ---------------- | ---------------------------------- |
| LangChain        | Implémentation RAG                 |
| Ollama (Mistral) | Modèle LLM local                   |             |
| PyPDF2          | Extraction du contenu PDF          |
| Python 3.12      | Langage principal                  |


---

## Installation & Exécution

### 1. Prérequis

* Python ≥ 3.12
* Ollama installé avec le modèle `mistral` chargé (`ollama pull mistral`)

### 2. Installation des dépendances

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Exécution

Étape 1 : Génération des embeddings

```bash
python RAG/rag_simple.py
```

Étape 2 : Lancement du RAG conversationnel

```bash
python RAG/rag_langchain.py
```

---

## Arborescence du projet

```
Simplon-mini-projet-LLM/
├── .venv/
├── data/
│   └── fichiers pdf
├── RAG/
│   ├── rag_simple.py          # Initialisation FAISS
│   └── rag_langchain.py       # Agent LangChain avec Mistral
├── requirements.txt
└── README.md
```

---

## Évaluation pédagogique

* Architecture RAG fonctionnelle avec Mistral via Ollama
* Vectorisation et récupération précise
* Code structuré et documenté

* Réponses précises et cohérentes aux requêtes utilisateurs
* Bonne couverture des cas d’usage : allergies, régimes spécifiques

* Livrables rendus dans les délais
* Respect des consignes (pas d’usage d’IA générative)
* Bonne autonomie sur un projet contraint et temps limité

---

## Retours & améliorations possibles

* Intégration d'une interface Gradio ou d'une API web pour la production
* Enrichissement de la base documentaire avec des cas réels
* Ajout d’un chat contextuel avec mémoire de session
* Optimisation du temps de réponse du LLM local

---

## Auteur

* [@Khadaassi](https://github.com/Khadaassi) — Simplon 2025

---

## Licence

Projet réalisé dans un cadre pédagogique (Simplon).
Utilisation libre à des fins d’apprentissage uniquement.
