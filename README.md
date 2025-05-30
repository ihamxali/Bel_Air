# Smart Inventory Management System
## Bel'Air Tandoori Restaurant - Besançon

A comprehensive, real-time inventory management system designed specifically for Bel'Air Tandoori Restaurant in Besançon, France. This system provides intelligent stock tracking, automated reorder alerts, and predictive analytics to optimize restaurant inventory operations.

## 🌟 Features

### Real-Time Stock Monitoring
- **Live Stock Levels**: Real-time tracking of all inventory items with visual progress indicators
- **Smart Status Indicators**: Color-coded status system (Critical, Low, Good, Overstocked)
- **Automated Alerts**: Instant notifications for critical and low stock situations
- **Weekly Usage Tracking**: Monitor consumption patterns for better forecasting

### Intelligent Reorder System
- **Smart Recommendations**: AI-powered suggestions based on usage patterns and minimum thresholds
- **One-Click Reordering**: Streamlined reorder process with pre-calculated quantities
- **Cost Estimation**: Automatic calculation of reorder costs before confirmation
- **Supplier Integration**: Direct supplier information for each inventory item

### Analytics & Forecasting
- **Usage Trend Analysis**: Visual charts showing weekly consumption patterns
- **Predictive Analytics**: Forecast when items will run out based on current usage
- **Performance Metrics**: KPI dashboard with total items, critical alerts, and inventory value
- **Historical Data Tracking**: Monitor inventory performance over time

### User-Friendly Interface
- **Modern Design**: Clean, responsive interface optimized for restaurant operations
- **Mobile Responsive**: Access from any device - desktop, tablet, or mobile
- **Quick Actions**: Fast access to critical functions like reordering
- **Visual Indicators**: Progress bars and color coding for instant status recognition

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager
- React environment

### Installation

1. **Clone the repository**
   ```bash
   git clone [https://github.com/ihamxali/Bel_Air_IMS]
   cd inventory-management-system
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Install required packages**
   ```bash
   npm install react recharts lucide-react
   # or
   yarn add react recharts lucide-react
   ```

4. **Start the development server**
   ```bash
   npm start
   # or
   yarn start
   ```

5. **Open your browser**
   Navigate to https://silver-axolotl-f36bf2.netlify.app to view the application

## 📊 System Components

### Dashboard Overview
- **KPI Cards**: Quick view of total items, critical alerts, inventory value, and reorder needs
- **Alert System**: Prominent display of critical and low stock warnings
- **Stock Status Table**: Comprehensive view of all inventory items with current levels

### Inventory Items Configuration
The system comes pre-configured with common Tandoori restaurant items:

| Item | Unit | Min Threshold | Max Capacity | Supplier |
|------|------|---------------|--------------|----------|
| Basmati Rice | kg | 20 | 100 | Delhi Spice Co. |
| Chicken Breast | kg | 15 | 50 | Fresh Meat Ltd |
| Tomatoes | kg | 10 | 40 | Local Farm |
| Garam Masala | kg | 5 | 20 | Spice Masters |
| Naan Mix | kg | 20 | 60 | Bread Supplies Inc |
| Yogurt | kg | 15 | 30 | Dairy Fresh |

### Stock Status Categories
- **🔴 CRITICAL**: Stock below 50% of minimum threshold - immediate action required
- **🟡 LOW**: Stock at or below minimum threshold - reorder recommended
- **🟢 GOOD**: Stock levels optimal
- **🟣 OVERSTOCKED**: Stock above 80% of maximum capacity

## 🔧 Customization

### Adding New Inventory Items
To add new items to the inventory, modify the `inventoryData` state in the component:

```javascript
{
  id: 7,
  item: 'New Item Name',
  currentStock: 10,
  minThreshold: 15,
  maxCapacity: 50,
  unit: 'kg',
  costPerUnit: 5.00,
  supplier: 'Supplier Name',
  lastOrdered: '2024-05-29',
  avgWeeklyUsage: 8
}
```

### Modifying Thresholds
Adjust the stock status thresholds in the `getStockStatus` function:

```javascript
const getStockStatus = (item) => {
  const stockRatio = item.currentStock / item.maxCapacity;
  
  if (item.currentStock <= item.minThreshold * 0.5) return 'critical';
  if (item.currentStock <= item.minThreshold) return 'low';
  if (stockRatio > 0.8) return 'overstocked';
  return 'good';
};
```

### Customizing Reorder Logic
Modify the `generateReorderSuggestion` function to adjust reorder calculations:

```javascript
const generateReorderSuggestion = (item) => {
  const suggestedOrder = Math.max(item.minThreshold * 2, item.avgWeeklyUsage * 4);
  return Math.min(suggestedOrder, item.maxCapacity - item.currentStock);
};
```

## 📱 Usage Guide

### Daily Operations
1. **Morning Check**: Review the dashboard for any critical or low stock alerts
2. **Stock Updates**: Update current stock levels as items are used or received
3. **Reorder Management**: Use the reorder recommendations to place orders
4. **Trend Analysis**: Review weekly usage trends to optimize purchasing

### Reordering Process
1. **Identify Items**: System automatically identifies items needing reorder
2. **Review Suggestions**: Check AI-generated quantity suggestions
3. **Confirm Orders**: Use one-click ordering with cost estimation
4. **Track Deliveries**: Update stock levels when deliveries arrive

### Weekly Review
- Analyze usage trends chart to identify patterns
- Review overstocked items to prevent waste
- Adjust minimum thresholds based on seasonal changes
- Update supplier information as needed

## 🛠️ Technical Details

### Built With
- **React**: Frontend framework for interactive UI
- **Recharts**: Data visualization and charting library
- **Lucide React**: Modern icon library
- **Tailwind CSS**: Utility-first CSS framework

### Key Functions
- `getStockStatus()`: Determines stock status based on current levels
- `generateReorderSuggestion()`: Calculates optimal reorder quantities
- `handleReorder()`: Manages the reorder process
- `processReorder()`: Updates inventory after order confirmation

### Data Structure
The system uses a comprehensive data model for each inventory item:
- Basic information (name, unit, supplier)
- Stock levels (current, minimum, maximum)
- Financial data (cost per unit)
- Usage analytics (weekly consumption, last order date)



## 🚀 Future Enhancements

### Planned Features
- **Supplier Integration**: Direct API connections with suppliers for automated ordering
- **Barcode Scanning**: Mobile app integration for quick stock updates
- **Advanced Analytics**: Machine learning predictions for seasonal demand
- **Multi-Location Support**: Manage inventory across multiple restaurant locations
- **Waste Tracking**: Monitor and reduce food waste through better forecasting

### Potential Integrations
- **POS System**: Automatic stock deduction based on sales
- **Accounting Software**: Direct integration with financial systems
- **Delivery Tracking**: Real-time delivery status updates
- **Mobile Notifications**: Push notifications for critical alerts



