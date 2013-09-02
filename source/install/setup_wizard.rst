Assistant de paramétrage
========================

Vous avez suivi la :doc:`première étape de l'installation <install>`. Les fichiers de Novius OS sont donc installés, le
serveur paramétré et vous accédez à http://votredomaine/novius-os/. Le plus dur est passé, la partie simple commence :-).

Étape 1 : Vérifier les prérequis
-------------------------------------

Cette étape devrait être une simple formalité si vous avez installé Novius OS avec la procédure d'installation rapide.
Dans les autres cas, si vous voyez beaucoup de rouge, ne vous inquiétez pas ! Le site a juste besoin de droits en
écriture dans certains répertoires. Cette étape vous donne des explications et les commandes à exécuter pour corriger
tous les points.

.. image:: images/setup_wizard/step-1a.png
	:alt: Étape 1a
	:align: center

Si vous ne voulez pas vous embêter, copiez / collez le résumé des commandes disponibles en bas de la page dans un terminal : c'est fini !

.. image:: images/setup_wizard/step-1b.png
	:alt: Étape 1b
	:align: center

Étape 2 : Configurer la base de données MySQL
---------------------------------------------

Vous avez besoin d'une base MySQL avec un utilisateur ayant les droits nécessaires. Dans le cas d'un hébergement
mutualisé, ces paramètres ont dû vous être fournis par votre hébergeur. Dans les autres cas, voici un exemple pour une
base en ``localhost`` :

.. code-block:: sql

    CREATE DATABASE `nom_de_votre_base` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
    GRANT ALL PRIVILEGES ON `nom_de_votre_base`.* TO 'nom_de_votre_utilisateur'@localhost IDENTIFIED BY 'mot_de_passe';
    FLUSH PRIVILEGES;

Remplissez les quatre champs demandés en fonction de la configuration de votre base.

Cette étape va créer deux fichiers :file:`local/config/db.php` et :file:`local/config/crypt.php` et, surtout, les tables
nécessaires dans votre base de données.

Étape 3 : Créer le premier compte administrateur
------------------------------------------------

Remplissez les champs demandés pour créer le premier compte administrateur de votre Novius OS.
L'email et le mot de passe vous serviront pour votre première connection.
Ces informations seront ensuite modifiables via le back-office.

Étape 4: Choix des langues
--------------------------------

Choisissez (ou ajoutez) les langues disponibles dans le front-office de votre site avant de finir l'installation.

.. image:: images/setup_wizard/step-4.png
	:alt: Étape 4
	:align: center

.. seealso::

    Concernant le paramétrage des contextes, reportez-vous aux :doc:`principes </understand/multi_context/principles>` et :ref:`à la documentation d'API <api:php/configuration/software/multi_contexts>`.


Applications
------------

Vous arrivez sur le gestionnaire d'applications. C'est ici que vous installez les applications dont vous avez besoin.

.. image:: images/setup_wizard/step-appmanager.png
	:alt: Gestionnaire d'applications
	:align: center

Se déconnecter / connecter
--------------------------

Pour vous déconnecter, cliquez sur votre prénom en haut à droite. Un menu apparait alors :

.. image:: images/setup_wizard/step-login-a.png
	:alt: Se déconnecter
	:align: center

Vous être alors redirigé sur le formulaire de connexion.

.. image:: images/setup_wizard/step-login-b.png
	:alt: Se connecter
	:align: center