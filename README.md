# TO DO LIST (Express, Babel, Sequelize, SQL) 


Installer express generator : npm install -g express-generator
express --view=pug newtodo
Entrer dans le dossier : cd newtodo
Refactoriser les variables du dossier routes et les fichiers index et user sur VScode, idem pour le bin changer toutes les variables (sur vs code faire ctrl+f, taper var + cliquer sur l’édredon en haut à gauche et remplacer par const)

Installer Babel : npm install @babel/core @babel/node --save-dev
Ouvrir dans VS code package.json, changer la ligne start par "start": "nodemon --exec babel-node ./bin/www"
Installation des presets de base de Babel : npm install @babel/preset-env --save-dev
Création du fichier de configuration pour Babel : touch .babelrc
Refactoriser les imports : Ouvrir avec VS code babelrc : code .babelrc puis copier dans le fichier  (récupération dans .babelrc (github Hachemi): 


Puis aller sur le repo H, récupérer le code suivant dans app.js (variable + import), à coller dans VsCode dans app.js : 


Installation du système de variables d'environnement : npm install dotenv-extended --save 
a. Création du fichier .env : touch .env 
b. Création de la première variable d'environnement dans le fichier .env : PORT=4000 
(en gros, les gars isolement des variables)

c. Test d'import + test du fonctionnement de dotenv 
puis aller sur le terminal et démarrer l’interface : npm start 
Remarque : si, cette manipulation crash faire un npm install, puis refaire un npm start.
Si le port ne fonctionne pas aller sur le terminal pour reset en faisant : rs puis relancer sur firefox et mettre localhost:4000

Ajout du template Bootstrap dans les pug views : 
Aller dans le repo de H, aller dans le fichier views
Copier le contenu du fichier index.pug puis coller sur vs code dans le fichier views > index.pg (remplacer celui-ci par le contenu déjà existant) 
Copier le contenu du fichier layout.pug puis coller sur vs code dans le fichier views > layout.pg (remplacer celui-ci par le contenu déjà existant) 


Aller sur le site https://scotch.io/tutorials/getting-started-with-node-express-and-postgres-using-sequelize

Aller à l’étape Sequilize Setup : 
Dans le terminal : 
npm install -g sequelize-cli
dans VS code sur le fichier .sequilizerc ajouter ceci : 


Dans le terminal à nouveau : 

$ npm install --save sequelize pg pg-hstore
$ sequelize init

Création de la base de données : 
sudo -u postgres psql (si la base n’est pas créée)
CREATE DATABASE todosdev; ⇐ pour créer une nouvelle base de données sur Psql 
Dans VScode, modifier dans server> config> confid.json 
ajouter ceci : 


sur le doc .env ajouter : 



Dans le terminal : 
$ sequelize model:create --name Todo --attributes title:string
Vérifier que dans VS code le fichier qu’un fichier à été créé dans migrations et dans models (todo.js)

Dans le terminal : 
$ sequelize model:create --name TodoItem --attributes content:string,complete:boolean

⇒ vérifier qu’un nouveau fichier apparait dans create to do items dans migrations
⇒ vérifier qu’un nouveau fichier apparait dans todoitems.js dans models

Dans le dossier models> todo.js : 
Modifier : 


Par 



Dans le dossier models> todoitem.js supprimer le contenu et remplacer par : 
Remarque : Ne pas supprimer le ‘use strict’



Dans le dossier migrations > createtodo, changer le contenu et remplacer par :
Remarque pas supprimer ‘use strict’; 




Dans le dossier migrations > createtodoitems, changer le contenu et remplacer par :
Remarque pas supprimer ‘use strict’; 



Dans le terminal VS code, créer le fichier controllers à l’intérieur le fichier de todos.js, à l’intérieur ajouter : 
‘use strict’; 


