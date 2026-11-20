# État de réalisation — MONTHLY TASK

## Fonctionnalités présentes dans le code
- [x] Socle React + TypeScript + Vite
- [x] Interface responsive PC / mobile
- [x] Application web installable (manifest + service worker)
- [x] Tableau de bord et indicateur de progression
- [x] Gestion des tâches : création, modification, suppression et validation
- [x] Gestion des objectifs avec priorité, échéance et durée estimée
- [x] Générateur de planning mensuel avec aperçu, jours disponibles, capacité quotidienne, priorités et échéances
- [x] Vues Aujourd'hui, À venir et Calendrier
- [x] Conservation des tâches terminées lors du remplacement d'un planning du même mois
- [x] Authentification e-mail Supabase (si projet configuré)
- [x] Synchronisation des tâches et objectifs Supabase (si migration et variables configurées)
- [x] Schéma PostgreSQL initial et politiques RLS
- [x] Rappels locaux Android pour les tâches sélectionnées
- [x] Configuration initiale Capacitor Android

## À terminer avant une livraison de production
- [ ] Édition complète des objectifs
- [x] Vues calendrier, aujourd'hui et à venir
- [ ] Vue Kanban
- [x] Rappels locaux Android à 8 h avec demande de permission
- [x] Notifications navigateur lorsque l’application est ouverte le jour de l’échéance
- [ ] Notifications web Push lorsque le navigateur est fermé
- [ ] Historique et statistiques détaillées
- [ ] Paramètres du profil et préférences
- [ ] Synchronisation robuste avec gestion des erreurs hors ligne et conflits
- [x] Tests automatisés du moteur de planification
- [ ] Tests de l’interface et des flux d’authentification
- [ ] Build web complet et contrôle de production
- [ ] Compilation APK/AAB et tests sur plusieurs versions Android

## Limites connues de cette archive
Le service Supabase doit être créé et configuré avec les variables d'environnement propres au déploiement. La compilation Android nécessite Android Studio, Android SDK et JDK 17. La compatibilité réelle doit être validée sur appareils et émulateurs.
