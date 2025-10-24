# Project Management Critical Path Analyzer

![Python](https://img.shields.io/badge/Python-3.7%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Stable-brightgreen)

A comprehensive Python application for project management that analyzes task dependencies, calculates critical paths, and generates Gantt charts with workforce allocation visualization.

## 📋 Overview

This tool processes project data from CSV files to:
- Validate project task dependencies and data integrity
- Calculate the critical path using network analysis
- Generate interactive Gantt charts highlighting critical tasks
- Visualize workforce allocation over time
- Identify potential project risks and bottlenecks

## ✨ Features

- **Data Validation**: Comprehensive CSV data validation with detailed error reporting
- **Dependency Analysis**: Detects cycles, missing dependencies, and structural issues
- **Critical Path Method**: Implements CPM for optimal project scheduling
- **Visualization**: Professional Gantt charts with critical path highlighting
- **Resource Management**: Workforce allocation tracking and optimization
- **User-Friendly**: Graphical file selection and detailed reporting

## 🚀 Installation

### Prerequisites
- Python 3.7 or higher
- Required packages (install via pip):

```bash
pip install pandas matplotlib networkx numpy tkinter
```

### Quick Start
1. Clone the repository:
```bash
git clone https://github.com/your-username/project-critical-path-analyzer.git
cd project-critical-path-analyzer
```

2. Run the application:
```bash
python project_analyzer.py
```

## 📁 Project Structure

```
project-critical-path-analyzer/
│
├── project_analyzer.py          # Main application file
├── sample_data.csv              # Example project data
├── requirements.txt             # Python dependencies
└── README.md                   # This file
```

## 📊 Input Format

Create your project data in CSV format with the following columns:

| Column | Description | Format | Example |
|--------|-------------|---------|---------|
| Work | Task identifier | String (unique) | `A`, `Task1` |
| Followers | Subsequent tasks | Comma-separated list | `B,C`, `D;E` |
| Predecessors | Previous tasks | Comma-separated list | `A`, `B;C` |
| Duration | Task duration | Positive number | `5`, `10.5` |
| Workforce | Required personnel | Non-negative number | `2`, `3.5` |

### Example CSV Format:
```csv
A, B;C, -, 3, 1
B, E, A, 11, 2
C, D;F, A, 4, 0
D, G;I, C, 7, 4
E, G;I, B, 3, 9
```

## 🛠️ Usage

### Running the Application

1. **Launch the application**:
   ```bash
   python project_analyzer.py
   ```

2. **Select your CSV file** through the graphical file dialog

3. **View validation results** - The tool will check for:
   - Data type consistency
   - Dependency validity
   - Cyclic dependencies
   - Missing tasks

4. **Analyze results** including:
   - Critical path identification
   - Project duration calculation
   - Workforce allocation
   - Interactive Gantt chart

### Output Features

- **Critical Path Visualization**: Red-highlighted tasks on Gantt chart
- **Workforce Allocation**: Bar chart showing personnel requirements over time
- **Detailed Reporting**: Task schedules, slack times, and resource usage
- **Error Diagnostics**: Comprehensive validation with line-by-line error reporting

## 🔍 Validation Features

The application performs extensive validation:

### Data Validation
- ✅ Numeric value checking for durations and workforce
- ✅ Unique task identifier verification
- ✅ Positive duration validation
- ✅ Non-negative workforce validation
- ✅ Proper dependency format checking

### Dependency Validation
- ✅ Cycle detection in task dependencies
- ✅ Missing task reference checking
- ✅ Self-dependency prevention
- ✅ Graph connectivity analysis
- ✅ Start/end task identification

## 📈 Output Examples

### Gantt Chart
- Critical path tasks in red
- Non-critical tasks in teal
- Task dependencies shown with arrows
- Duration labels on each task bar

### Workforce Chart
- Daily personnel requirements
- Peak load identification
- Resource allocation optimization

### Text Report
```
Critical Path: A → B → E → G → H → K → M → N
Project Duration: 45 days
Max Workforce: 15 people
Critical Tasks: 8 of 15 total tasks
```

## 🐛 Error Handling

The application provides detailed error messages:

```
✗ Errors found in CSV data:
  1. Line 3, column 'Duration': Invalid numeric value 'seven'
  2. Line 5, column 'Workforce': Workforce cannot be negative (received -2)
  3. Line 7: Predecessor 'X' for task 'G' does not exist
  4. Circular dependency detected: A -> B -> C -> A
```

## 💡 Use Cases

- **Project Managers**: Schedule optimization and resource planning
- **Construction**: Critical path analysis for building projects
- **Software Development**: Sprint planning and dependency management
- **Event Planning**: Timeline creation and resource allocation
- **Academic Projects**: Teaching critical path methodology

## 🎯 Key Algorithms

- **Topological Sorting**: For task scheduling
- **Critical Path Method (CPM)**: For path calculation
- **Early/Late Start/Finish**: For slack time calculation
- **Network Analysis**: For dependency validation

## 🤝 Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

If you encounter any issues:

1. Check the error messages for specific line numbers in your CSV
2. Ensure all task references exist in the 'Work' column
3. Verify numeric formats in duration and workforce columns
4. Check for circular dependencies in your task relationships

## 🔮 Future Enhancements

- [ ] Web-based interface
- [ ] Export to PDF/Excel functionality
- [ ] Multiple project comparison
- [ ] Risk analysis integration
- [ ] Real-time collaboration features

---

**Developed with ❤️ for efficient project management**

*For questions and support, please open an issue in the GitHub repository.*
