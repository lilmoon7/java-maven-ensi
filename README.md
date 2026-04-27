# TP 2 : Jenkins via Docker

**Nom & Prénom :** Niema El Malki  
**Module :** DevOps & Automation  
**Filière :** Licence Développement Informatique et Méthodes DevOps  
**Université :** Abdelmalek Essaâdi — Faculté Polydisciplinaire de Larache  
**Année Universitaire :** 2025/2026  

---

## Objectif

L'objectif de ce TP est d'installer Jenkins sur une machine locale en utilisant **Docker**,
puis de configurer un pipeline CI/CD connecté à un dépôt GitHub avec un Webhook.

---

## Prérequis

- Docker Desktop installé
- Git installé
- Minimum 2 Go de RAM
- 10 Go d'espace disque disponible

---

Builder l'image jenkins principal 
<img width="1920" height="1008" alt="image" src="https://github.com/user-attachments/assets/f29e53d5-1589-4dd5-8388-f221dcc3b277" />

Demarer le conteneure myjenkins
<img width="1259" height="102" alt="image" src="https://github.com/user-attachments/assets/aa3895f1-0da3-4557-a740-db42d641b565" />

Recuper le mot de passe de jenkins 
<img width="991" height="81" alt="image" src="https://github.com/user-attachments/assets/b211b0aa-9ead-44d3-9643-39de053808f7" />

instalation ...
<img width="994" height="951" alt="Screenshot 2026-04-27 002246" src="https://github.com/user-attachments/assets/e330eaab-6c17-402d-b11c-19abc14cc096" />

creation de pipline pipelineJava
<img width="1919" height="934" alt="image" src="https://github.com/user-attachments/assets/619fe564-491f-4f5f-b9e9-2c6c7be3a6c7" />

<img width="1651" height="848" alt="image" src="https://github.com/user-attachments/assets/5b61d90c-d541-4523-a20f-2d43f945e851" />
Lors de l'exécution du pipeline, deux erreurs ont été rencontrées : la première est l'absence du socket Docker (/var/run/docker.sock) dans
le conteneur Jenkins, ce qui empêche toute communication avec le daemon Docker ;
la seconde est l'impossibilité d'accéder à l'image my-maven-git:latest, qui en découle directement.
La solution adoptée a été de relancer le conteneur Jenkins en montant explicitement le socket Docker via
l'option -v /var/run/docker.sock:/var/run/docker.sock.
<img width="1184" height="327" alt="image" src="https://github.com/user-attachments/assets/e5f5c19b-bc20-4153-8037-5f517dda315b" />



