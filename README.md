# MONTHLY TASK

Application de planification mensuelle, conçue pour le navigateur sur PC et pour Android via Capacitor.

## État de cette version

Cette version comprend :
- tableau de bord responsive PC / mobile ;
- création, modification, validation et suppression des tâches ;
- création et suppression des objectifs, avec priorité, échéance et durée estimée ;
- vues Aujourd'hui, À venir et Calendrier ;
- générateur de planning mensuel avec aperçu, jours disponibles, capacité quotidienne, priorités et échéances ;
- authentification e-mail et synchronisation Supabase, lorsque le projet cloud est configuré ;
- rappels locaux Android à 8 h sur les tâches choisies ;
- application web installable (PWA) et cache de base pour l'ouverture hors ligne.

Sans configuration Supabase, les données restent locales à l'appareil (`localStorage`). Dans un navigateur, les rappels sont affichés lorsque l'application est ouverte le jour de l'échéance. Les notifications web lorsque le navigateur est fermé nécessitent un service Push côté serveur.

## Prérequis

- Node.js LTS
- npm
- Pour Android : Android Studio, Android SDK et JDK 17

## Lancer sur PC

```bash
npm install
npm run dev
```

Ouvrir l'adresse locale affichée par Vite dans le navigateur.

## Construire la version web

```bash
npm run build
```

Les fichiers de production sont créés dans `dist/`.

## Préparer Android

Après installation d'Android Studio et configuration du SDK :

```bash
npm install
npx cap add android
npm run android:sync
npm run android:open
```

Dans Android Studio, lancer l'application sur un émulateur ou un téléphone connecté. Pour produire un APK : Build > Build Bundle(s) / APK(s) > Build APK(s).

## Synchronisation cloud

Le schéma initial et les politiques RLS se trouvent dans `supabase/migrations/0001_initial_schema.sql`. Exécuter cette migration dans le SQL Editor du projet Supabase avant de configurer l’application. Ne jamais placer de clé `service_role` dans l’application cliente.

## Comptes et synchronisation Supabase

Le client Supabase est activé lorsque `VITE_SUPABASE_URL` et `VITE_SUPABASE_ANON_KEY` sont renseignées. Sans ces variables, l'application reste en mode local sur l'appareil. Avec Supabase configuré et la migration SQL appliquée, les utilisateurs peuvent créer un compte, se connecter et synchroniser leurs objectifs et tâches. Chaque utilisateur est isolé par les politiques RLS.

Pour configurer l'environnement : copier `.env.example` vers `.env.local`, renseigner les deux variables publiques du projet Supabase, puis redémarrer Vite.

## Tests

```bash
npm test
```

Les tests du générateur couvrent les jours disponibles, la durée des séances, la capacité journalière et les cas de configuration impossibles.
