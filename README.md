# API DevHub Connect

## Description

Bienvenue dans la documentation de notre API RESTful pour notre base de données de projets, utilisateurs et compétences. Cette API vous permet de créer, lire, mettre à jour et supprimer des informations relatives aux utilisateurs, aux projets, aux candidatures, aux compétences et aux emplacements. Elle est construite en utilisant les normes REST et est accessible via des requêtes HTTP standard. Les données sont retournées au format JSON pour une utilisation facile dans n'importe quelle application ou site web. Dans les sections suivantes, nous allons détailler les différentes fonctionnalités et routes de l'API ainsi que les exemples de requêtes et de réponses.

## Endpoints :

**Utilisateurs :**
Endpoint : /users

- Méthode : GET
    - Description : Récupère une liste de tous les utilisateurs
    - Réponse : Liste des utilisateurs avec les champs id, firstname, lastname, email, biography, about, user_image, github_page, experience, user_role_id, job_id et location_id
- Méthode : POST
    - Description : Ajoute un nouvel utilisateur
    - Requête : Champs firstname, lastname, email, biography, about, user_image, password, github_page, experience, user_role_id, job_id et location_id
    - Réponse : ID de l'utilisateur ajouté
- Méthode : PUT
    - Description : Met à jour un utilisateur existant
    - Requête : ID de l'utilisateur à mettre à jour et les champs à mettre à jour (firstname, lastname, email, biography, about, user_image, password, github_page, experience, user_role_id, job_id et location_id)
    - Réponse : Message de confirmation de la mise à jour
- Méthode : DELETE
    - Description : Supprime un utilisateur existant
    - Requête : ID de l'utilisateur à supprimer
    - Réponse : Message de confirmation de la suppression

**Candidatures :**
- Méthode : GET
    - Description : Récupère une liste de toutes les candidatures
    - Réponse : Liste des candidatures avec les champs user_id, project_id, apply_date, user_status et user_motivation
- Méthode : POST
    - Description : Ajoute une nouvelle candidature
    - Requête : Champs user_id, project_id, apply_date, user_status et user_motivation
    - Réponse : ID de la candidature ajoutée
- Méthode : PUT
    - Description : Met à jour une candidature existante
    - Requête : ID de la candidature à mettre à jour et les champs à mettre à jour (user_id, project_id, apply_date, user_status et user_motivation)
    - Réponse : Message de confirmation de la mise à jour
- Méthode : DELETE
    - Description : Supprime une candidature existante
    - Requête : ID de la candidature à supprimer
    - Réponse : Message de confirmation de la suppression

**Projets :**
- Récupérer tous les projets : ***GET /projects***
- Récupérer un projet par ID : ***GET /projects/:id***
- Créer un projet : ***POST /projects***
- Mettre à jour un projet : ***PUT /projects/:id***
- Supprimer un projet : ***DELETE /projects/:id***

**Compétences utilisateur :**
- Récupérer toutes les compétences utilisateur : ***GET /user_skills***
- Récupérer une compétence utilisateur par ID : ***GET /user_skills/:id***
- Créer une compétence utilisateur : ***POST /user_skills***
- Mettre à jour une compétence utilisateur : ***PUT /user_skills/:id***
- Supprimer une compétence utilisateur : ***DELETE /user_skills/:id***

**Compétences projet :**
- Récupérer toutes les compétences projet : ***GET /project_skills***
- Récupérer une compétence projet par ID : ***GET /project_skills/:id***
- Créer une compétence projet : ***POST /project_skills***
- Mettre à jour une compétence projet : ***PUT /project_skills/:id***
- Supprimer une compétence projet : ***DELETE /project_skills/:id***

**Emplois :**
- Récupérer tous les emplois : ***GET /jobs***
- Récupérer un emploi par ID : ***GET /jobs/:id***
- Créer un emploi : ***POST /jobs***
- Mettre à jour un emploi : ***PUT /jobs/:id***
- Supprimer un emploi : ***DELETE /jobs/:id***

**Rôles utilisateur :**
- Récupérer tous les rôles utilisateur : ***GET /user_roles***
- Récupérer un rôle utilisateur par ID : ***GET /user_roles/:id***
- Créer un rôle utilisateur : ***POST /user_roles***
- Mettre à jour un rôle utilisateur : ***PUT /user_roles***
- Supprimer un rôle utilisateur :***DELETE /user_roles***



## Exemple Utilisateurs

### Récupérer tous les utilisateurs

Requête :

```
GET /users
```

Réponse :

```
{
    "users": [
        {
            "id": 1,
            "firstname": "John",
            "lastname": "Doe",
            "email": "johndoe@example.com",
            "biography": "Je suis développeur web",
            "about": "Je suis passionné par le développement web depuis plusieurs années...",
            "user_image": "https://example.com/images/1.jpg",
            "password": "hashed_password",
            "github_page": "https://github.com/johndoe",
            "experience": 5,
            "user_role_id": 1,
            "job_id": 1,
            "location_id": 1
        },
        {
            "id": 2,
            "firstname": "Jane",
            "lastname": "Smith",
            "email": "janesmith@example.com",
            "biography": "Je suis développeur mobile",
            "about": "Je suis passionné par le développement mobile depuis plusieurs années...",
            "user_image": "https://example.com/images/2.jpg",
            "password": "hashed_password",
            "github_page": "https://github.com/janesmith",
            "experience": 3,
            "user_role_id": 2,
            "job_id": 2,
            "location_id": 2
        }
    ]
}
```

### Récupérer un utilisateur par son ID

Requête :

```
GET /users/:id
```

Réponse :

```
{
    "id": 1,
    "firstname": "John",
    "lastname": "Doe",
    "email": "johndoe@example.com",
    "biography": "Je suis développeur web",
    "about": "Je suis passionné par le développement web depuis plusieurs années...",
    "user_image": "https://example.com/images/1.jpg",
    "password": "hashed_password",
    "github_page": "https://github.com/johndoe",
    "experience": 5,
    "user_role_id": 1,
    "job_id": 1,
    "location_id": 1
}
```

### Ajouter un utilisateur

Requête :

```
POST /users
```

Avec un corps de requête :

```
{
  "firstname": "John",
  "lastname": "Doe",
  "email": "johndoe@email.com",
  "biography": "A software developer with 5 years of experience.",
  "about": "I am a motivated and passionate developer who is always looking to improve my skills and learn new technologies.",
  "user_image": "image_data_as_a_blob",
  "password": "password_hash",
  "github_page": "https://github.com/johndoe",
  "experience": 5,
  "user_role_id": 1,
  "job_id": 2,
  "location_id": 3
}
```

### Mise à jour d'un utilisateur

Requête :

```
PUT https://example.com/api/users/42

Body :
{
    "firstname": "John",
    "lastname": "Doe",
    "email": "johndoe@example.com",
    "biography": "A software developer with 10 years of experience.",
    "about": "I love coding and I'm always looking for new challenges.",
    "user_image": "https://example.com/images/johndoe.jpg",
    "password": "mysecretpassword",
    "github_page": "https://github.com/johndoe",
    "experience": 10,
    "user_role_id": 2,
    "job_id": 1,
    "location_id": 5
}
```

Avec un corps de requête :

```
HTTP/1.1 200 OK

Body :
{
    "id": 42,
    "firstname": "John",
    "lastname": "Doe",
    "email": "johndoe@example.com",
    "biography": "A software developer with 10 years of experience.",
    "about": "I love coding and I'm always looking for new challenges.",
    "user_image": "https://example.com/images/johndoe.jpg",
    "password": "mysecretpassword",
    "github_page": "https://github.com/johndoe",
    "experience": 10,
    "user_role_id": 2,
    "job_id": 1,
    "location_id": 5
}
```

### Effacer un utilisateur

Requête :

```
DELETE https://api.example.com/users/42
```

Avec un corps de requête :

```
HTTP/1.1 200 OK
```
