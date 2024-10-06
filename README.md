<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Code Python & IA</title>
    <link rel="shortcut icon" href="./logo-2150297_1280.webp">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #f5f5f5, #e2d4c3); /* Dégradé de gris clair à beige */
            background-attachment: fixed;
            color: #333; /* Couleur du texte principal */
            display: flex;
            flex-direction: column;
            min-height: 100vh; /* Assure que le corps prend au moins la hauteur de la fenêtre */
        }

        header {
            background-color: #d4a373; /* Beige doré */
            color: #ffffff;
            padding: 30px 20px; /* Augmentation du padding pour un effet plus spacieux */
            text-align: center;
            border-bottom-left-radius: 50% 30px; /* Rayon plus grand pour un effet plus doux */
            border-bottom-right-radius: 50% 30px;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: "";
            position: absolute;
            top: -60px; /* Déplacement vers le haut pour varier l'emplacement */
            left: -60px;
            width: 200px; /* Taille augmentée pour plus de variation */
            height: 200px;
            background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, rgba(255,255,255,0) 100%);
            border-radius: 50%;
            z-index: -1;
            opacity: 0.5;
        }

        main {
            padding: 20px;
            flex: 1; /* Permet au main de prendre l'espace restant disponible */
        }

        section {
            background: #ffffff; /* Blanc */
            border-radius: 12px; /* Coins arrondis plus marqués */
            box-shadow: 0 8px 16px rgba(0,0,0,0.3); /* Ombre plus marquée */
            padding: 20px;
            margin-bottom: 20px;
            position: relative;
            overflow: hidden;
            z-index: 1; /* Assure que les éléments sont au-dessus des formes de fond */
        }

        section::before {
            content: "";
            position: absolute;
            top: -50px; /* Déplacement vers le haut pour varier l'emplacement */
            left: -70px;
            width: 180px; /* Taille ajustée pour plus de variation */
            height: 180px;
            background: radial-gradient(circle, rgba(0,0,0,0.1) 0%, rgba(0,0,0,0.2) 100%);
            border-radius: 50%;
            z-index: -1;
            transform: rotate(-10deg); /* Rotation pour plus de dynamisme */
            display: none; /* Enlève un rond sur deux en alternant */
        }

        section:nth-of-type(even)::before {
            display: block; /* Affiche un rond sur deux */
        }

        section::after {
            content: "";
            position: absolute;
            bottom: -40px; /* Déplacement vers le bas pour varier l'emplacement */
            right: -40px;
            width: 160px; /* Taille ajustée pour plus de variation */
            height: 160px;
            background: linear-gradient(135deg, #d4a373, #f5f5f5);
            border-radius: 50%;
            z-index: -1;
            transform: rotate(10deg); /* Rotation pour plus de dynamisme */
        }

        h1 {
            font-size: 2.5em; /* Taille du titre principale */
            margin: 0;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2); /* Ombre portée pour plus de profondeur */
        }

        h2 {
            font-size: 1.8em; /* Taille des sous-titres */
            margin-top: 0;
            margin-bottom: 15px;
            font-weight: bold;
            color: #d4a373; /* Couleur du texte des sous-titres */
            text-shadow: 1px 1px 3px rgba(0,0,0,0.1); /* Ombre portée douce pour le texte */
        }

        p {
            line-height: 1.6; /* Hauteur de ligne augmentée pour une meilleure lisibilité */
            margin: 0 0 20px; /* Marge inférieure pour espacer les paragraphes */
        }

        pre {
            background-color: #2e2e2e; /* Gris foncé */
            color: #f8f8f2; /* Gris clair */
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
            position: relative;
            z-index: 1;
        }

        pre::before {
            content: "";
            position: absolute;
            top: -10px;
            left: -10px;
            width: calc(100% + 20px);
            height: calc(100% + 20px);
            background: radial-gradient(circle, rgba(0,0,0,0.1) 0%, rgba(0,0,0,0.1) 50%, rgba(0,0,0,0.2) 100%);
            border-radius: 10px;
            z-index: -1;
        }

        footer {
            background-color: #d4a373; /* Beige doré */
            color: #ffffff;
            text-align: center;
            padding: 10px;
            border-top-left-radius: 50% 30px; /* Rayon plus grand pour un effet plus doux */
            border-top-right-radius: 50% 30px;
            width: 100%;
            box-sizing: border-box;
            position: relative;
        }

        .bold {
            font-weight: bold; /* Texte en gras */
        }

        .intro-text {
            font-weight: normal; /* Texte normal par défaut */
            color: #ffffff; /* Couleur du texte en blanc */
            margin-top: 20px; /* Marge au-dessus du texte d'introduction */
        }

        .spyder-info {
            color: #000000; /* Couleur du texte sur Spyder en noir */
            margin-bottom: 40px;
        }

        /* Styles pour le troisième code IA */
        .third-code-ia {
            background: linear-gradient(145deg, #ffffff, #f7f7f7); /* Gradient très léger pour ajouter du relief */
            border: 1px solid #e0e0e0; /* Bordure légèrement plus claire */
            padding: 20px; /* Augmentation du padding pour plus d'espace interne */
            border-radius: 10px; /* Coins légèrement plus arrondis */
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1); /* Ombre douce et plus diffuse */
            margin-bottom: 50px; /* Augmente l'espace entre les sections */
            transition: transform 0.3s ease, box-shadow 0.3s ease; /* Ajout d'une transition fluide */
        }

        /* Effet au survol */
        .third-code-ia:hover {
            box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15); /* Ombre plus marquée au survol */
            transform: translateY(-5px); /* Légère élévation au survol */
        }

        /* Style css navigation */
        nav {
    background-color: #e1cfb7; /* Beige intermédiaire pour la barre de navigation */
    padding: 15px 0;
    margin-bottom: 20px;
    width: 100%;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    text-align: center;
}

nav ul li {
    display: inline-block;
    margin: 0 20px;
}

nav ul li a {
    color: #262524; /* Marron foncé pour les liens */
    text-decoration: none;
    font-size: 1.1rem;
    font-weight: bold; /* Titres en gras */
    text-shadow: 0.5px 0.5px 0 #fff, -0.5px -0.5px 0 #fff, 0.5px -0.5px 0 #fff, -0.5px 0.5px 0 #fff; /* Détourage léger en blanc */
    text-transform: uppercase;
    padding: 10px 15px;
    transition: background-color 0.3s ease;
}

nav ul li a:hover {
    background-color: #ece1cd; /* Beige clair au survol */
    color: #8b7d6b; /* Beige foncé */
    border-radius: 5px;
}

.codes-ia p {
    color: #000; /* Noir pour le texte */
    
}
    </style>
    
    <style>
        
        
    </style>
    <script type="text/javascript" src="https://translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>
    <script type="text/javascript">
        function googleTranslateElementInit() {
            new google.translate.TranslateElement({
                pageLanguage: 'fr',
                includedLanguages: 'en,fr',
                layout: google.translate.TranslateElement.InlineLayout.SIMPLE
            }, 'google_translate_element');
        }

        
    </script>
    <style>
        #google_translate_element {
            position: absolute;
            top: 10px;
            right: 10px;
            z-index: 1000; /* Pour s'assurer que l'élément reste visible */
        }
    </style>
</head>
</head>
<body>
    <header>
       
       
        <div id="google_translate_element"></div>
        <!-- Reste du contenu du header -->
        <header>
          
        </header>
        
        <h1><span class="bold">Bienvenue</span> sur <span class="bold">Code Python & IA</span></h1>
        <p class="intro-text">Notre site est conçu pour vous fournir des <span class="bold">codes Python</span> simples et gratuits à copier-coller, spécialement pour des applications d'<span class="bold">intelligence artificielle</span>. Que vous soyez débutant curieux d'utiliser l'IA ou professionnel dans le milieu cherchant une base de programme, Vous trouverez ici des <span class="bold">exemples pratiques</span> que vous pouvez utiliser immédiatement dans vos projets. Chaque code est accompagné de <span class="bold">conseils</span> sur ce qu'il faut faire avant de l'exécuter, comme l'<span class="bold">installation de bibliothèques</span> nécessaires ou la configuration de votre environnement de développement. Les codes et téléchargements sont conçus pour <span class="bold">Spyder</span>, un environnement de développement intégré pour Python. Nous avons simplifié le processus pour que vous puissiez vous concentrer sur l'<span class="bold">apprentissage</span> et l'<span class="bold">expérimentation</span>, tout en recevant des <span class="bold">explications utiles</span> pour chaque morceau de code.</p>

        <nav>
            <ul>
                <li><a href="index.html">Accueil</a></li>
                <li><a href="equipe.html">A propos de nous</a></li>
                <li><a href="codes.html">Code IA</a></li>
                <li><a href="conseils.html">Conseils</a></li>
                <li><a href="contacts.html">Contact</a></li>
            </ul>
        </nav>

        <section class="spyder-info">
            <h2><span class="bold">Installer Spyder</span></h2>
            <p>Pour utiliser les codes fournis sur notre site, nous vous recommandons d'installer Spyder, un environnement de développement intégré (IDE) pour Python. Voici comment procéder :</p>
            <ol>
                <li><strong>Téléchargez l'installateur :</strong> Rendez-vous sur le site officiel de <a href="https://docs.spyder-ide.org/current/installation/" target="_blank" class="bold">Spyder</a> et téléchargez l'installateur approprié pour votre système d'exploitation.</li>
                <li><strong>Exécutez l'installateur :</strong> Double-cliquez sur le fichier téléchargé et suivez les instructions à l'écran pour installer Spyder.</li>
                <li><strong>Configurez Spyder :</strong> Une fois l'installation terminée, lancez Spyder. Vous pouvez personnaliser les paramètres selon vos préférences.</li>
                <li><strong>Installez les bibliothèques nécessaires :</strong> Utilisez la console intégrée dans Spyder pour installer les bibliothèques nécessaires à vos projets.</li>
                <li><strong>Utilisez les codes :</strong> Copiez les codes fournis sur notre site et collez-les dans l'éditeur de Spyder pour les exécuter.</li>
            </ol>
        </section>
        <section class="codes-ia">
            <h2><span class="bold">Les Codes IA du Mois</span></h2>
            <p>Découvrez ici les codes Python liés à l'intelligence artificielle qui sont recommandés pour ce mois. Ils sont faciles à copier et à utiliser dans vos projets ! <strong> A noter :</strong>Si vous rencontrez des difficultés diverses liées à l'exécution du code ou autres, cliquez sur la section "conseils".</p>
        </section>
    </header>
    <main>
        <section>
            <h2><span class="bold"></span> IA pour Révision - Extraction de Mots-Clés et Génération de Moyens Mnémotechniques</h2>
            <p>Ce code Python utilise une IA pour extraire des mots-clés d'un texte, identifier le thème principal et générer des moyens mnémotechniques pour aider à la révision. Voici un exemple à copier-coller dans l'éditeur de code de Spyder situé sur la gauche de votre écran :</p>
            <pre><code>
        import spacy
        from collections import Counter
        from scipy.spatial.distance import cosine
        import sqlite3
        from nltk.corpus import wordnet as wn
        from nltk.data import find
        
        # Chargement des données nécessaires pour WordNet
        try:
            find('corpora/omw-1.4.zip')
        except LookupError:
            import nltk
            nltk.download('omw-1.4')
            nltk.download('wordnet')
        
        nlp = spacy.load("fr_core_news_md")
        
        def explain_sentence(sentence):
            # Fonction fictive pour remplacer la fonctionnalité GPT
            # Remplacez cette fonction par la logique de votre choix
            return f"Explication simplifiée de la phrase : {sentence}"
        
        def identify_main_theme(text):
            # Fonction fictive pour remplacer la fonctionnalité GPT
            # Remplacez cette fonction par la logique de votre choix
            return f"Thème principal du texte : {text}"
        
        # Connexion à la base de données
        def connect_db(db_path):
            return sqlite3.connect(db_path)
        
        # Vérification de la structure de la base de données
        def check_database_structure(db_connection):
            cursor = db_connection.cursor()
            cursor.execute("SELECT name FROM sqlite_master WHERE type='table' AND name='mnemonic_associations';")
            table_exists = cursor.fetchone()
            if table_exists:
                print("Table 'mnemonic_associations' trouvée.")
            else:
                print("Table 'mnemonic_associations' non trouvée.")
        
        def search_database(concept, db_connection):
            cursor = db_connection.cursor()
            query = "SELECT association FROM mnemonic_associations WHERE concept = ?;"
            cursor.execute(query, (concept,))
            rows = cursor.fetchall()
            return [row[0] for row in rows]
        
        def preprocess_text(text):
            doc = nlp(text)
            lemmatized_words = [
                token.lemma_.lower() for token in doc 
                if token.is_alpha and not token.is_stop and token.pos_ != "VERB"  # Exclure les verbes
            ]
            return lemmatized_words
        
        def extract_concepts(words, num_concepts=10):
            word_freq = Counter(words)
            return word_freq.most_common(num_concepts)
        
        def get_synonyms(word):
            synonyms = set()
            for syn in wn.synsets(word, lang='fra'):
                for lemma in syn.lemmas(lang='fra'):
                    synonyms.add(lemma.name())
            return list(synonyms)[:3]  # Limiter à 3 synonymes
        
        def get_similar_words(word, threshold=0.3, max_similar_words=3):
            word_vec = nlp.vocab[word].vector
            if word_vec is None or all(val == 0 for val in word_vec):
                return []
            
            similar_words = []
            for w in nlp.vocab:
                if w.has_vector and w.is_lower and w.is_alpha and w.text != word:
                    similarity = 1 - cosine(word_vec, w.vector)
                    if similarity > threshold:
                        similar_words.append((w.text, similarity))
            
            similar_words.sort(key=lambda x: x[1], reverse=True)
            return [word for word, _ in similar_words[:max_similar_words]]
        
        def generate_associations(concepts, db_connection):
            amorçages = []
            
            # Convertir les concepts en une chaîne de texte pour l'IA
            text_for_theme = " ".join([concept for concept, _ in concepts])
            
            # Identifie le thème principal
            main_theme = identify_main_theme(text_for_theme)
            
            for concept, _ in concepts:
                # Associations basées sur le texte
                prefix_associations = generate_prefix_associations(concept)
                amorçage_texte = f"Associe '{concept}' avec les mots suivants (texte) : {prefix_associations if prefix_associations else 'Aucune association trouvée.'}"
                
                # Associations dans la base de données
                db_associations = search_database(concept, db_connection)
                amorçage_db = f"Associe '{concept}' avec les mots suivants (base de données) : {', '.join(db_associations) if db_associations else 'Aucune association trouvée.'}"
                
                # Associations ConceptNet
                conceptnet_associations = get_similar_words(concept)
                amorçage_conceptnet = f"Associe '{concept}' avec les mots suivants (ConceptNet) : {', '.join(conceptnet_associations) if conceptnet_associations else 'Aucune association trouvée.'}"
                
                # Synonymes
                synonyms = get_synonyms(concept)
                amorçage_synonymes = f"Associe '{concept}' avec les synonymes suivants : {', '.join(synonyms) if synonyms else 'Aucun synonyme trouvé.'}"
                
                amorçages.append(
                    f"Thème principal : {main_theme}\n\n"
                    f"{amorçage_texte}\n\n"
                    f"{amorçage_db}\n\n"
                    f"{amorçage_conceptnet}\n\n"
                    f"{amorçage_synonymes}"
                )
            
            return amorçages
        
        def generate_prefix_associations(word):
            associations = []
            
            # Ajoutez des règles plus variées pour enrichir les associations
            if word.startswith("révo"):
                associations.append("révolution -> changement")
            elif word.startswith("auto"):
                associations.append("automatique -> autonomie")
            elif word.startswith("pol"):
                associations.append("politique -> gouvernance")
            
            return ", ".join(associations) if associations else None
        
        def main():
            text = input("Entrez le texte de votre leçon : ")
            db_path = "path_to_your_database.db"
            db_connection = connect_db(db_path)
            
            # Vérifier la structure de la base de données
            check_database_structure(db_connection)
        
            preprocessed_text = preprocess_text(text)
            concepts = extract_concepts(preprocessed_text)
            
            print("Concepts clés extraits :")
            for concept, freq in concepts:
                print(f"{concept}: {freq}")
            
            amorçages = generate_associations(concepts, db_connection)
            
            print("\nAmorçages mnémotechniques :")
            for amorçage in amorçages:
                print(amorçage)
            
            db_connection.close()
        
        if __name__ == "__main__":
            main()
            </code></pre>
            <p><strong>Instructions :</strong> Avant d'exécuter ce code, assurez-vous d'avoir installé les bibliothèques nécessaires en utilisant les commandes suivantes dans la console de Spyder située en bas à droite. Pour installer, copiez-collez la commande et appuyez sur Entrée (Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.):</p>
            <pre><code>!pip install spacy scipy sqlite3 nltk</code></pre>
            <p>Vous devrez également télécharger le modèle SpaCy et les ressources NLTK. Pour ce faire, utilisez (Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.):</p>
            <pre><code>!python -m spacy download fr_core_news_md</code></pre>
            <p><strong>Conseil :</strong> Il est possible que des erreurs apparaissent dans la console même après avoir installé les bibliothèques nécessaires. Dans ce cas, ne paniquez pas. Montrez cette erreur à ChatGPT, qui vous expliquera les installations nécessaires supplémentaires pour utiliser le code. Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.</p>
        </section>
        


        <section>
            <h2><span class="bold"></span> IA pour Résumé de Textes</h2>
            <p>Ce code utilise des modèles avancés de traitement du langage naturel pour transformer des textes longs et complexes en résumés concis et pertinents. Que ce soit pour des documents académiques, des articles de recherche ou des informations professionnelles, elle extrait les points essentiels tout en maintenant la cohérence et la clarté. Voici un exemple à copier-coller dans l'éditeur de code de Spyder situé sur la gauche de votre écran :</p>
            <pre><code>
                # Importer les bibliothèques
                from transformers import BartForConditionalGeneration, BartTokenizer
                
                # Charger le modèle BART et le tokenizer
                model_name = "facebook/bart-large-cnn"
                model = BartForConditionalGeneration.from_pretrained(model_name)
                tokenizer = BartTokenizer.from_pretrained(model_name)
                
                # Fonction de génération de résumé
                def generate_summary(prompt, max_length=130, min_length=30):
                    inputs = tokenizer(prompt, return_tensors="pt", max_length=1024, truncation=True)
                    
                    # Générer le résumé
                    summary_ids = model.generate(
                        inputs['input_ids'],
                        max_length=max_length,
                        min_length=min_length,
                        length_penalty=2.0,
                        num_beams=4,
                        early_stopping=True
                    )
                    
                    # Décoder le résumé
                    summary = tokenizer.decode(summary_ids[0], skip_special_tokens=True)
                    
                    return summary
                
                # Demander à l'utilisateur d'entrer un texte de départ
                user_input = input("Entrez un texte de départ : ")
                
                # Générer un résumé
                summary = generate_summary(user_input)
                
                # Afficher le résumé
                print("\nRésumé généré :\n")
                print(summary)
                
            </code></pre>
            <p><strong>Instructions :</strong> Avant d'exécuter ce code, assurez-vous d'avoir installé les bibliothèques nécessaires en utilisant les commandes suivantes dans la console de Spyder située en bas à droite. Pour installer, copiez-collez la commande et appuyez sur Entrée (Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.):</p>
            <pre><code>!pip install transformers torch</code></pre>
            <p>Vous devrez également télécharger les modèles requis. Pour ce faire, utilisez (Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder):</p>
            <pre><code>!python -m transformers-cli download gpt2-medium</code></pre>
            <p><strong>Conseil :</strong> Il est possible que des erreurs apparaissent dans la console même après avoir installé les bibliothèques nécessaires. Dans ce cas, ne paniquez pas. Montrez cette erreur à ChatGPT, qui vous expliquera les installations nécessaires supplémentaires pour utiliser le code. Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.</p>
        </section>
        <!-- 3ème exemple -->
    <div class="third-code-ia">
        <h2><span class="bold"></span> Générateur de Questions</h2>
            <p>Ce code Python utilise un modèle pré-entraîné pour générer des questions à partir d'un texte donné. Voici un exemple à copier-coller dans l'éditeur de code de Spyder situé sur la gauche de votre écran :</p>
            <pre><code>
                from transformers import pipeline

                # Charger le modèle de génération de questions
                question_generator = pipeline("text2text-generation", model="valhalla/t5-small-qg-hl")
                
                # Demander à l'utilisateur d'entrer le texte
                context_text = input("Veuillez entrer le texte : ")
                
                # Générer plusieurs questions avec recherche par faisceau
                questions = question_generator(context_text, max_length=50, num_return_sequences=3, num_beams=5)
                
                # Afficher les questions générées
                print("\nQuestions générées :")
                for question in questions:
                    formatted_question = question['generated_text'].strip() + "?"
                    print(formatted_question)  # Ajout d'un point d'interrogation
                    print()  # Ligne vide pour séparer les questions
                
            </code></pre>
            <p><strong>Instructions :</strong> Avant d'exécuter ce code, assurez-vous d'avoir installé les bibliothèques nécessaires en utilisant les commandes suivantes dans la console de Spyder située en bas à droite. Pour installer, copiez-collez la commande et appuyez sur Entrée (Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.):</p>
            <pre><code>!pip install transformers</code></pre>
            
            <p><strong>Conseil :</strong> Il est possible que des erreurs apparaissent dans la console même après avoir installé les bibliothèques nécessaires. Dans ce cas, ne paniquez pas. Montrez cette erreur à ChatGPT, qui vous expliquera les installations nécessaires supplémentaires pour utiliser le code. Assurez-vous également de placer un "!" devant le code d'installation car vous êtes sur Spyder.</p>
      <div>
        
        <!-- Répéter les autres exemples de la même manière -->
        
       
    </main>
    <footer>
        <p>&copy; 2024 Code Python & IA. Tous droits réservés.</p>
    </footer>
    
</body>
</html>


