# Assistant Bankily (RAG) 🏦

Ce projet est un assistant intelligent basé sur l'architecture **RAG (Retrieval-Augmented Generation)**, conçu pour répondre aux questions concernant les services de **Bankily** et de la **Banque Populaire de Mauritanie (BPM)**.

L'assistant est capable de répondre aux questions en **français** et en **arabe**, en s'appuyant sur une base de connaissances officielle (fichiers Markdown).

## 🚀 Fonctionnalités
- **Recherche Hybride** : Combine la recherche sémantique (FAISS + BGE-M3) et la recherche par mots-clés (BM25) pour une précision maximale.
- **Re-ranking** : Utilise un modèle Cross-Encoder pour affiner les résultats de recherche et sélectionner les documents les plus pertinents.
- **Génération (LLM)** : Intègre **Mistral-7B-Instruct** (quantifié en 4-bit) pour générer des réponses naturelles et précises basées sur le contexte récupéré.
- **Multilingue** : Support complet du français et de l'arabe.
- **Interface Moderne** : Une interface conversationnelle élégante construite avec **Gradio**, fonctionnant nativement dans Google Colab.
- **Évaluation** : Intègre un pipeline d'évaluation scientifique (Precision@k, Recall@k, Fidélité via BERTScore, ROUGE) pour valider les performances du système.

## 📂 Structure du projet
- `RAG_Bankily_Clean.ipynb` : Le notebook Jupyter principal contenant tout le code (chargement des données, configuration des modèles, logique RAG, évaluation et interface Gradio).
- `FR/` : Dossier contenant la base de connaissances en français (fichiers `.md`).
- `AR/` : Dossier contenant la base de connaissances en arabe (fichiers `.md`).
- `requirements.txt` : Liste des dépendances Python nécessaires.

## 🛠️ Installation et Exécution

### Sur Google Colab (Recommandé)
1. Importez le fichier `RAG_Bankily_Clean.ipynb` dans Google Colab.
2. Assurez-vous d'activer un environnement d'exécution **GPU (T4)**.
3. Importez les dossiers `FR/` et `AR/` dans l'espace de stockage de Colab.
4. Exécutez les cellules du notebook une par une.
5. La dernière cellule générera un lien public (`.gradio.live`) pour accéder à l'interface.

### En Local
1. Clonez ce dépôt :
   ```bash
   git clone <URL_DU_DEPOT>
   cd bankily_knowledge_base
   ```
2. Créez un environnement virtuel et installez les dépendances :
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Lancez le notebook Jupyter localement ou exécutez le script.

## 📊 Évaluation
Le système a été évalué sur un jeu de 20 questions de test. Les métriques incluent :
- **Precision@3** et **Recall@3** pour évaluer la qualité du moteur de recherche.
- **BERTScore (F1)** pour évaluer la fidélité de la réponse générée par rapport à une réponse attendue (Ground Truth).
- **Temps de réponse moyen**.

## 🎓 Contexte
Ce projet a été réalisé dans le cadre d'un projet de recherche (Université de Nouakchott — FST · 2026).
