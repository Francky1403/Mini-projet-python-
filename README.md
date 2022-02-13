# Mini-projet-python
# Commencer
Installation des Dépendances

Python 3.9.8

pip 22.0.3 from 

C:\Users\midek\AppData\Local\Programs\Python\Python39\lib\site-packages\pip (python 3.9)

Suivez les instructions suivantes pour installer l'ancienne version de python sur
la plateforme  python docs

  ##Dépendances de PIP

Pour installer les dépendances, ouvrez le dossier /Documentation et exécuter la 
commande suivante:

        pip install -r requirements.txt
        or
        pip3 install -r requirements.txt

Nous passons donc à l'installation de tous les packages se trouvant dans le 
fichier requirements.txt.

clé de Dépendances

    Flask est un petit framework web Python léger, qui fournit des outils et des         fonctionnalités utiles qui facilitent la création d’applications web en Python.

    SQLAlchemy est un toolkit open source SQL et un mapping objet-relationnel écrit en Python et publié sous licence MIT. SQLAlchemy a opté pour l'utilisation du pattern Data Mapper plutôt que l'active record utilisés par de nombreux autres ORM

    Flask-CORS is the extension we'll use to handle cross origin requests from our frontend server.
# Démarrer le serveur

Pour démarrer le serveur sur Linux ou Mac, executez:

      export FLASK_APP=app.py
      export FLASK_ENV=development
      flask run
      
 Pour le démarrer sur Windows, executez:
 
      set FLASK_APP=app.py
      set FLASK_ENV=development
      flask run
# API REFERENCE

Démarrer

URL de base : à l’heure actuelle, cette application ne peut être exécutée que localement et n’est pas hébergée en tant qu’URL de base. L’application backend est hébergée par défaut, http://localhost:5000 ; qui est défini comme proxy dans la configuration frontale.
# Type d'erreur

Les erreurs sont renvoyées sou forme d'objet au format Json: { "success":False "error": 400 "message":"Ressource non disponible" }

L'API vous renvoie 4 types d'erreur: . 400: Bad request ou ressource non disponible . 500: Internal server error . 422: Unprocessable . 404: Not found
# Endpoints
. ## OBTENIR/livres

      GENERAL:
           Cet endpoint retourne la liste des objets livres, la valeur du succès et le        total des livres. 

    
      EXEMPLE: curl http://localhost:5000/livres


                   {
                  "livres":[
                   {
                        "auteur": "Divhope", 
                        "date_pub": "Wed, 21 Jul 1920 00:00:00 GMT", 
                        "editeur": "KGB", 
                        "id": 1, 
                        "isbn": "LH1", 
                        "titre": "premiere guerre mondial"
                    }, 
                    {
                      "auteur": "Aghata Christie", 
                      "date_pub": "Thu, 20 Sep 1990 00:00:00 GMT", 
                      "editeur": "WIlliam", 
                      "id": 2, 
                      "isbn": "RP1", 
                      "titre": "le crime de lorient express"
                    }, 
                    {
                      "auteur": "Hippolyte", 
                      "date_pub": "Mon, 23 Mar 2020 00:00:00 GMT", 
                      "editeur": "BG", 
                      "id": 3, 
                      "isbn": "S1", 
                      "titre": "Le cyle de la vie"
                    }, 
                    {
                      "auteur": "George", 
                      "date_pub": "Thu, 24 Dec 2020 00:00:00 GMT", 
                      "editeur": "espace", 
                      "id": 4, 
                      "isbn": "G1", 
                      "titre": "univers"
                    }, 
                    {
                      "auteur": "Pitagore", 
                      "date_pub": "Wed, 06 Jun 1770 00:00:00 GMT", 
                      "editeur": "Phenom\u00e8ne", 
                      "id": 6, 
                      "isbn": "klnknkonpk", 
                      "titre": "Espace Vectoriel"
                    }, 
                    {
                      "auteur": "ramirez", 
                      "date_pub": "Thu, 13 Mar 1980 00:00:00 GMT", 
                      "editeur": "temps", 
                      "id": 7, 
                      "isbn": "LH2", 
                      "titre": "deuxieme guerre mondial"
                    }, 
                    {
                      "auteur": "pablo escobar", 
                      "date_pub": "Thu, 13 Mar 1980 00:00:00 GMT", 
                      "editeur": "crime", 
                      "id": 8, 
                      "isbn": "RP2", 
                      "titre": "le pouvoir ou rien"
                    }, 
                    {
                      "auteur": "DAMSO", 
                      "date_pub": "Thu, 19 Apr 2018 00:00:00 GMT", 
                      "editeur": "DG", 
                      "id": 9, 
                      "isbn": "S2", 
                      "titre": "les microbes"
                    }, 
                    {
                      "auteur": "Ismal", 
                      "date_pub": "Sat, 20 Feb 2016 00:00:00 GMT", 
                      "editeur": "Terre", 
                      "id": 10, 
                      "isbn": "G2", 
                      "titre": "Les roches"
                    }, 
                    {
                      "auteur": "Arnaud", 
                      "date_pub": "Thu, 16 Apr 2015 00:00:00 GMT", 
                      "editeur": "Cercle", 
                      "id": 11, 
                      "isbn": "M2", 
                      "titre": "les fonctions"
                    }, 
                    {
                      "auteur": "Razade", 
                      "date_pub": "Fri, 06 Jul 1770 00:00:00 GMT", 
                      "editeur": "Liminus", 
                      "id": 13, 
                      "isbn": "PC3", 
                      "titre": "oxygene"
                    }, 
                    {
                      "auteur": "Riva", 
                      "date_pub": "Mon, 06 Dec 1999 00:00:00 GMT", 
                      "editeur": "Hist", 
                      "id": 14, 
                      "isbn": "H4", 
                      "titre": "De la terre a la lune"
                    }
                 ],
    
              "status_code": 200,
              "success": true,
              "total_books": 4
          }
          
          
.##GET/livres(id)

          GENERAL: 
              Cet endpoint permet de récupérer les informations d'un livre particulier s'il existe par le biais de l'ID.  

          EXEMPLE: http://localhost:5000/livres/2
          


              {
                "auteur": "Aghata Christie", 
                "date_pub": "Thu, 20 Sep 1990 00:00:00 GMT", 
                "editeur": "WIlliam", 
                "id": 2, 
                "isbn": "RP1", 
                "titre": "le crime de lorient express"
              }          



. ## SUPPRIMER/livres (id)

        GENERAL:
            Supprimer un element si l'ID existe. Retourne l'ID du livre supprimé, la    valeur du succès et le nouveau total.

            EXEMPLE: curl -X DELETE http://localhost:5000/livres/4


          {
              "delete succefully": 13,
              "success": true
          }
          

. ##PATCH/categories(id_cat) 

      GENERAL:
          Cet endpoint permet de mettre à jour,le libelle d'une categorie. Il retourne une categorie mis à jour.


EXEMPLE..... Avec Patch

        {
          "id_cat": 6, 
          "libelle_cat": "Science_Physique"
        }

  
      
          EXEMPLE: curl -X UPDATE http://localhost:5000/categories/6
  

           {
                    "id_cat": 6, 
                    "libelle_cat": "Science_Physique"
                  }=>
                  {
              "categorie": {
                  "id_cat": 6,
                  "libelle_cat": "Science_P"
              },
              "success modify": true
          }


.##GET/categories(id_cat)/livres 

    GENERAL: 
          Cet endpoint permet de lister la liste des livres contenues dans une categorie 

          EXEMPLE: http://localhost:5000/categories/4/livres
          
          
          [
              {
                "auteur": "George", 
                "date_pub": "Thu, 24 Dec 2020 00:00:00 GMT", 
                "editeur": "espace", 
                "id": 4, 
                "isbn": "G1", 
                "titre": "univers"
              }, 
              {
                "auteur": "Ismal", 
                "date_pub": "Sat, 20 Feb 2016 00:00:00 GMT", 
                "editeur": "Terre", 
                "id": 10, 
                "isbn": "G2", 
                "titre": "Les roches"
              }
            ]
