# Dashboard Gantt pour Chantiers de Construction

Un dashboard de diagramme de Gantt professionnel et interactif pour la gestion de projets de construction. Parfait pour suivre les chantiers complexes avec plusieurs phases, dépendances et coordination d'équipes.

## Fonctionnalités

✨ **Diagramme de Gantt Interactif**
- Glisser-déposer pour reprogrammer les tâches
- Suivi en temps réel de la progression
- Visualisation des dépendances entre tâches
- Structure hiérarchique avec phases extensibles

📊 **Vue d'ensemble du Projet**
- Suivi de progression en temps réel
- Surveillance budgétaire (réel vs. budgétisé)
- Suivi des jalons (milestones)
- Visualisation de l'allocation des ressources

🎯 **Gestion des Tâches**
- Phases extensibles avec sous-tâches
- Indicateurs de statut (Complétée, En cours, En attente)
- Code couleur par type de tâche
- Barres de progression avec pourcentage

⚡ **Interactions Avancées**
- Redimensionner les barres de tâches pour ajuster la durée
- Glisser les tâches pour les reprogrammer
- Infobulle au survol avec détails
- Cliquer pour développer/réduire les phases
- Zoom sur la timeline (vues mensuelle/hebdomadaire/quotidienne)

🔄 **Mises à Jour en Temps Réel**
- Mises à jour statut des tâches en direct
- Vérification automatique des dépendances
- Identification du chemin critique
- Ajustement automatique de la timeline

## Structure des Fichiers

```
├── index.html              # Application dashboard principale
├── gantt-data.json         # Données d'exemple du projet
├── README.md               # Documentation anglaise
├── README-FR.md            # Documentation française
└── images/
    └── dashboard-preview.png  # Illustration avant/après
```

## Démarrage Rapide

### Utilisation Basique

1. **Charger le Dashboard**
   - Ouvrir `index.html` dans un navigateur moderne
   - Le dashboard charge automatiquement les données d'exemple

2. **Comprendre la Mise en Page**
   - **Panneau gauche**: Liste des tâches avec phases et sous-tâches
   - **Panneau droit**: Visualisation de la timeline (diagramme de Gantt)
   - **En-tête**: Vue d'ensemble du projet et métriques
   - **Bas de page**: Légende et contrôles

3. **Interagir avec les Tâches**
   - **Cliquer sur le nom de phase** pour développer/réduire les sous-tâches
   - **Glisser la barre de tâche** pour reprogrammer
   - **Redimensionner la barre** (bord droit) pour changer la durée
   - **Survoler** les tâches pour voir les détails
   - **Double-cliquer** pour éditer les propriétés

## Format des Données

### Objet Projet

```json
{
  "project": {
    "name": "Nom du Projet",
    "client": "Nom du Client",
    "location": "Localisation",
    "startDate": "2024-01-15",
    "endDate": "2024-06-30",
    "budget": 250000,
    "budgetUsed": 187500,
    "progress": 72
  }
}
```

### Objet Tâche

```json
{
  "id": 1,
  "name": "Phase 1: Préparation",
  "type": "phase",
  "startDate": "2024-01-15",
  "endDate": "2024-01-31",
  "progress": 100,
  "status": "completed",
  "color": "#10b981",
  "dependencies": [],
  "assignee": "Manager",
  "subtasks": [
    {
      "id": 1.1,
      "name": "Sous-tâche 1",
      "startDate": "2024-01-15",
      "endDate": "2024-01-20",
      "progress": 100,
      "status": "completed"
    }
  ]
}
```

## Valeurs de Statut

- **completed**: Tâche terminée (vert)
- **in-progress**: Tâche en cours (bleu)
- **pending**: Tâche non démarrée (gris)
- **at-risk**: Tâche en retard (orange/rouge)

## Compatibilité Navigateurs

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Navigateurs mobiles modernes

## Personnalisation

### Couleurs

Modifiez la propriété `color` dans les données JSON ou modifiez les variables CSS :

```css
--color-completed: #10b981;
--color-in-progress: #3b82f6;
--color-pending: #9ca3af;
--color-phase-1: #f97316;
```

### Granularité Timeline

Changez la granularité dans le JavaScript :
- **Quotidienne**: `timelineGranularity = 'daily'`
- **Hebdomadaire**: `timelineGranularity = 'weekly'` (défaut)
- **Mensuelle**: `timelineGranularity = 'monthly'`

## API & Méthodes

```javascript
// Actualiser les données
gantt.loadData(newProjectData);

// Obtenir une tâche par ID
const task = gantt.getTask(taskId);

// Mettre à jour la progression
gantt.updateTaskProgress(taskId, 50);

// Ajouter une dépendance
gantt.addDependency(fromTaskId, toTaskId);

// Exporter en PDF/PNG
gantt.exportChart('pdf');
```

## Performance

- Gère efficacement les projets avec 100+ tâches
- Défilement virtuel pour les grands ensembles de données
- Rendu optimisé
- Interactions glisser-déposer fluides

## Responsive Mobile

Le dashboard est entièrement responsive et fonctionne sur les tablettes et appareils mobiles avec support des gestes tactiles.

## Dépannage

### Les tâches ne s'affichent pas
- Vérifiez le format des données JSON
- Assurez-vous que les dates sont au format ISO (YYYY-MM-DD)
- Vérifiez que les ID des tâches sont uniques

### Le glisser-déposer ne fonctionne pas
- Activez JavaScript dans votre navigateur
- Videz le cache du navigateur
- Essayez un navigateur différent

### Problèmes de performance
- Réduisez le nombre de tâches visibles
- Utilisez la vue mensuelle pour les longs projets
- Fermez les onglets de navigateur inutiles

## Support & Documentation

Pour plus d'informations sur les diagrammes de Gantt et la gestion de projet :
- [Guide Diagramme de Gantt](https://fr.wikipedia.org/wiki/Diagramme_de_Gantt)
- [Bonnes Pratiques en Gestion de Projet](https://www.pmi.org/)

## Licence

Ce dashboard est fourni tel quel pour usage commercial et personnel.

## Version

Version 1.0.0 - Janvier 2024

---

**Idéal pour les PMO, entreprises de construction, entrepreneurs et chefs de projet qui ont besoin d'une solution de diagramme de Gantt professionnelle et prête à l'emploi.**
