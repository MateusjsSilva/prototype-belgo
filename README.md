# Inventory Management System

A modern, single-page application (SPA) for managing inventory, stock movements, and generating reports. Built with vanilla JavaScript, Tailwind CSS, and Chart.js.

## Features

### Dashboard
- **Overview Statistics**: View total items, low stock alerts, and total inventory value
- **Stock Levels Chart**: Visual representation of top 5 items by stock quantity using Chart.js
- **Recent Movements**: Quick view of the latest inventory transactions

### Inventory Management (Insumos)
- **CRUD Operations**: Create, read, update, and delete inventory items
- **Real-time Search**: Filter inventory items by name
- **Stock Monitoring**: Visual indicators for items below minimum stock levels
- **Product Details**: Track SKU, unit, price, minimum stock, and current balance

### Stock Movements (Movimentações)
- **Entry/Exit Tracking**: Record inventory entries and exits
- **Transaction History**: Complete audit trail of all stock movements
- **Advanced Filtering**: Search by product name and filter by movement type (Entry/Exit)
- **Automatic Stock Updates**: Stock levels automatically adjust when movements are recorded

### Reports (Relatórios)
- **CSV Export**: Generate and download movement reports in CSV format
- **Date Range Filtering**: Export movements for specific date ranges
- **Excel-Compatible**: CSV files include BOM (Byte Order Mark) for proper Excel encoding

### User Management (Usuários)
- **User Administration**: Add and remove authorized users
- **Role Management**: Assign Admin or User roles
- **Email Validation**: Ensures valid email addresses for user accounts

## Technology Stack

- **HTML5**: Semantic markup
- **CSS3**: Styling with Tailwind CSS (via CDN)
- **JavaScript (ES6+)**: Vanilla JavaScript with modern features
- **Chart.js**: Data visualization for stock levels
- **Tailwind CSS**: Utility-first CSS framework for responsive design

## Getting Started

### Prerequisites

No build tools or dependencies required. This is a pure client-side application that runs directly in the browser.

### Installation

1. Clone the repository:
```bash
git clone https://github.com/MateusjsSilva/prototype-belgo.git
cd prototype-belgo
```

2. Open `index.html` in a modern web browser:
   - Simply double-click the file, or
   - Use a local web server (recommended for development):
     ```bash
     # Using Python 3
     python -m http.server 8000
     
     # Using Node.js (http-server)
     npx http-server
     
     # Using PHP
     php -S localhost:8000
     ```

3. Navigate to `http://localhost:8000` in your browser

## Usage

### Adding Inventory Items

1. Navigate to **Insumos** (Inventory) section
2. Click **"Adicionar Insumo"** (Add Item) button
3. Fill in the form:
   - Product name (required)
   - Unit of measurement (required)
   - SKU (optional)
   - Unit price (required)
   - Minimum stock level (required)
4. Click **"Salvar"** (Save)

### Recording Stock Movements

1. Navigate to **Movimentações** (Movements) section
2. Click **"Registrar Entrada"** (Record Entry) or **"Registrar Saída"** (Record Exit)
3. Select the product from the dropdown
4. Enter quantity, date, and optional invoice/requisition number
5. Click **"Registrar"** (Register)

The system automatically validates that sufficient stock exists before allowing an exit.

### Generating Reports

1. Navigate to **Relatórios** (Reports) section
2. Optionally select a date range (leave blank for all movements)
3. Click **"Gerar CSV"** (Generate CSV)
4. The file will download automatically with a timestamped filename

### Managing Users

1. Navigate to **Usuários** (Users) section
2. Click **"Adicionar Usuário"** (Add User) to create a new user
3. Enter email and select role (Admin or User)
4. Click the delete icon to remove a user

## Code Structure

The application follows a modular structure:

```
index.html
├── HTML Structure
│   ├── Sidebar Navigation
│   ├── Main Content Area
│   └── Modal Component
└── JavaScript Application
    ├── Utility Functions
    │   ├── HTML Escaping (XSS Prevention)
    │   ├── Currency Formatting
    │   ├── Date Formatting
    │   └── Validation Functions
    ├── Data Storage
    │   ├── Inventory Items (insumos)
    │   ├── Movements (movimentacoes)
    │   └── Users (usuarios)
    ├── Routing & Navigation
    ├── Page Rendering Functions
    ├── Chart Initialization
    ├── Modal Handling
    ├── Event Listeners
    ├── Form Handling & Validation
    └── CSV Export
```

## Security Features

- **XSS Prevention**: All user input is escaped using `escapeHtml()` function
- **Input Validation**: Comprehensive validation for all form inputs
- **Email Validation**: Regex-based email format validation
- **Number Validation**: Ensures positive numbers for quantities and prices

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Opera (latest)

## Contributing

Contributions are welcome. Please feel free to submit a Pull Request.

## License

See the [LICENSE](LICENSE) file for details.
