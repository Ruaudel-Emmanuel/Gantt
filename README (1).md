# Construction Gantt Dashboard

A professional, interactive Gantt chart dashboard for construction project management. Perfect for tracking complex building projects with multiple phases, dependencies, and team coordination.

## Features

✨ **Interactive Gantt Chart**
- Drag-and-drop task rescheduling
- Real-time progress tracking
- Task dependencies visualization
- Hierarchical task structure 

📊 **Project Overview**
- Real-time progress tracking
- Budget monitoring (actual vs. budgeted)
- Milestone tracking
- Resource allocation view

🎯 **Task Management**
- Expandable phases with subtasks
- Status indicators (Completed, In Progress, Pending)
- Color-coded task types
- Progress bars with percentage display

⚡ **Advanced Interactions**
- Resize task bars to adjust duration
- Drag tasks to reschedule
- Hover for detailed task information
- Click to expand/collapse phases
- Zoom timeline (monthly/weekly/daily views)

🔄 **Real-time Updates**
- Live task status updates
- Automatic dependency checking
- Critical path identification
- Automatic timeline adjustment

## File Structure

```
├── index.html              # Main dashboard application
├── gantt-data.json         # Sample project data
├── README.md               # English documentation
├── README-FR.md            # French documentation
└── images/
    └── dashboard-preview.png  # Before/After illustration
```

## Getting Started

### Basic Usage

1. **Load the Dashboard**
   - Open `index.html` in a modern web browser
   - The dashboard loads sample data automatically

2. **Understanding the Layout**
   - **Left Panel**: Task list with phases and subtasks
   - **Right Panel**: Timeline visualization (Gantt chart)
   - **Header**: Project overview and metrics
   - **Bottom**: Legend and controls

3. **Interact with Tasks**
   - **Click phase name** to expand/collapse subtasks
   - **Drag task bar** to reschedule
   - **Resize task bar** (right edge) to change duration
   - **Hover** over tasks to see details
   - **Double-click** to edit task properties

### Loading Custom Data

To use your own project data:

```javascript
// Modify the data loading in index.html
const projectData = {
  project: { /* your project info */ },
  tasks: [ /* your tasks */ ],
  milestones: [ /* your milestones */ ]
};
```

## Data Format

### Project Object

```json
{
  "project": {
    "name": "Project Name",
    "client": "Client Name",
    "location": "Location",
    "startDate": "2024-01-15",
    "endDate": "2024-06-30",
    "budget": 250000,
    "budgetUsed": 187500,
    "progress": 72
  }
}
```

### Task Object

```json
{
  "id": 1,
  "name": "Phase 1: Preparation",
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
      "name": "Subtask 1",
      "startDate": "2024-01-15",
      "endDate": "2024-01-20",
      "progress": 100,
      "status": "completed"
    }
  ]
}
```

## Status Values

- **completed**: Task finished (green)
- **in-progress**: Task currently running (blue)
- **pending**: Task not yet started (gray)
- **at-risk**: Task behind schedule (orange/red)

## Browser Compatibility

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Modern mobile browsers

## Customization

### Colors

Edit the task `color` property in JSON data or modify CSS variables:

```css
--color-completed: #10b981;
--color-in-progress: #3b82f6;
--color-pending: #9ca3af;
--color-phase-1: #f97316;
```

### Timeline Scale

Change the timeline granularity in the JavaScript:
- **Daily**: `timelineGranularity = 'daily'`
- **Weekly**: `timelineGranularity = 'weekly'` (default)
- **Monthly**: `timelineGranularity = 'monthly'`

## API & Methods

```javascript
// Refresh data
gantt.loadData(newProjectData);

// Get task by ID
const task = gantt.getTask(taskId);

// Update task progress
gantt.updateTaskProgress(taskId, 50);

// Add dependency
gantt.addDependency(fromTaskId, toTaskId);

// Export to PDF/PNG
gantt.exportChart('pdf');
```

## Performance

- Handles projects with 100+ tasks efficiently
- Virtual scrolling for large datasets
- Optimized rendering
- Smooth drag-and-drop interactions

## Mobile Responsive

The dashboard is fully responsive and works on tablets and mobile devices with touch gesture support.

## Troubleshooting

### Tasks not showing
- Check JSON data format
- Verify dates are in ISO format (YYYY-MM-DD)
- Ensure task IDs are unique

### Drag-drop not working
- Enable JavaScript in your browser
- Clear browser cache
- Try a different browser

### Performance issues
- Reduce number of visible tasks
- Use monthly view for long projects
- Close unnecessary browser tabs

## Support & Documentation

For more information about Gantt charts and project management:
- [Gantt Chart Guide](https://en.wikipedia.org/wiki/Gantt_chart)
- [Project Management Best Practices](https://www.pmi.org/)

## License

This dashboard is provided as-is for commercial and personal use.

## Version

Version 1.0.0 - January 2024

---

**Perfect for PMOs, construction companies, contractors, and project managers who need a professional, ready-to-use Gantt chart solution.**
