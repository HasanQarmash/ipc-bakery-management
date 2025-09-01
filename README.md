# 🥐 Real-Time Bakery Management Simulation

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/HasanQarmash/ipc-bakery-management)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OpenGL](https://img.shields.io/badge/graphics-OpenGL-orange.svg)](https://www.opengl.org/)
[![C](https://img.shields.io/badge/language-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![IPC](https://img.shields.io/badge/IPC-POSIX-green.svg)](https://en.wikipedia.org/wiki/Inter-process_communication)

> A sophisticated multi-process simulation system that models a complete bakery operation using advanced inter-process communication (IPC) mechanisms and real-time OpenGL visualization.

## 🎯 Overview

This project implements a comprehensive real-time bakery management simulation that demonstrates advanced concepts in:
- **Multi-process Programming** using POSIX IPC
- **Real-time Systems** with synchronized operations
- **Resource Management** and inventory control
- **Interactive Visualization** with OpenGL/GLUT
- **Configuration-driven Architecture**

The simulation models a complete bakery ecosystem with different types of staff (chefs, bakers, sellers, supply chain), dynamic customer behavior, and intelligent management decisions.

## ✨ Key Features

### 🏭 Multi-Process Architecture
- **6 Chef Types**: Paste, Cake, Sandwich, Sweet, Sweet Patisserie, Savory Patisserie
- **3 Baker Types**: Cake & Sweet, Patisserie, Bread specialists
- **Dynamic Staff**: Configurable sellers and supply chain employees
- **Customer Generator**: Realistic customer arrival patterns with patience simulation
- **Management System**: AI-driven decision making for resource optimization

### 🎨 Real-Time Visualization
- **Live Production Graphs**: Real-time bar charts showing production vs. sales
- **Inventory Monitoring**: Visual inventory levels with threshold warnings
- **Performance Metrics**: Profit tracking, customer satisfaction, operational efficiency
- **Color-coded Status**: Intuitive visual feedback for all bakery operations

### 🔧 Advanced IPC Implementation
- **Shared Memory**: For real-time data sharing between processes
- **Semaphores**: For synchronized access to critical resources
- **Message Queues**: For customer requests and management communications
- **Process Synchronization**: Ensuring data consistency across all operations

### 📊 Intelligent Management
- **Dynamic Resource Allocation**: Automatic chef reassignment based on demand
- **Supply Chain Optimization**: Smart inventory replenishment
- **Customer Satisfaction Monitoring**: Real-time tracking of service quality
- **Performance Analytics**: Comprehensive business metrics

## 🏗️ System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Chef Teams    │    │  Baker Teams    │    │  Seller Team    │
│                 │    │                 │    │                 │
│ • Paste Chefs   │    │ • Cake & Sweet  │    │ • Customer      │
│ • Cake Chefs    │    │ • Patisserie    │    │   Service       │
│ • Sandwich      │    │ • Bread         │    │ • Order         │
│ • Sweet         │    │                 │    │   Processing    │
│ • Patisseries   │    │                 │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                    ┌─────────────────┐
                    │ Management Core │
                    │                 │
                    │ • IPC Coordination
                    │ • Resource Mgmt  │
                    │ • Decision AI    │
                    │ • Analytics      │
                    └─────────────────┘
                                 │
                    ┌─────────────────┐
                    │ Visualization   │
                    │                 │
                    │ • OpenGL        │
                    │ • Real-time     │
                    │ • Interactive   │
                    └─────────────────┘
```

## 🛠️ Technical Implementation

### IPC Mechanisms Used
- **Shared Memory Segments**: For inventory and production status
- **POSIX Semaphores**: For thread-safe operations
- **Message Queues**: For asynchronous communication
- **Process Forking**: For concurrent operation simulation

### Product Categories
- 🍞 **Bread**: 3 varieties with wheat, yeast, butter
- 🥪 **Sandwiches**: 5 types requiring bread and cheese/salami
- 🎂 **Cakes**: 4 flavors using complex ingredient combinations
- 🍯 **Sweets**: 6 flavors with sugar and sweet items
- 🥐 **Patisseries**: Sweet (4 types) and Savory (3 types) specialties

### Smart Features
- **Dynamic Pricing**: Base prices configurable per product type
- **Patience Simulation**: Customers have realistic waiting thresholds
- **Complaint System**: Customer feedback mechanism
- **Resource Thresholds**: Intelligent inventory management
- **Production Optimization**: Efficient workflow management

## 🚀 Quick Start

### Prerequisites
```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install build-essential freeglut3-dev

# CentOS/RHEL/Fedora
sudo yum install gcc freeglut-devel
# or
sudo dnf install gcc freeglut-devel

# macOS (with Homebrew)
brew install freeglut
```

### Installation & Running

1. **Clone the repository**
   ```bash
   git clone https://github.com/HasanQarmash/ipc-bakery-management.git
   cd ipc-bakery-management
   ```

2. **Build the project**
   ```bash
   make clean && make
   ```

3. **Run the simulation**
   ```bash
   make run
   # or manually:
   ./bin/bakery_simulation config/bakery_config.txt
   ```

4. **Watch the magic happen!** 🎭
   - The OpenGL window will open showing real-time bakery operations
   - Console output will display process startup and operational logs
   - Watch production graphs update live as the bakery operates

## ⚙️ Configuration

The simulation is highly configurable via `config/bakery_config.txt`:

### Staff Configuration
```ini
NUM_PASTE_CHEFS=2
NUM_CAKE_CHEFS=2
NUM_SELLERS=4
NUM_SUPPLY_CHAIN_EMPLOYEES=3
```

### Product & Pricing
```ini
BREAD_BASE_PRICE=3.5
CAKE_BASE_PRICE=15.0
NUM_CAKE_FLAVORS=4
```

### Customer Behavior
```ini
CUSTOMER_ARRIVAL_MIN_INTERVAL=8
CUSTOMER_PATIENCE_MAX_SECONDS=45
CUSTOMER_COMPLAINT_PROBABILITY=0.1
```

### Business Thresholds
```ini
FRUSTRATED_CUSTOMER_THRESHOLD=20
PROFIT_THRESHOLD=1000
SIMULATION_MAX_TIME_MINUTES=30
```

## 📊 Performance Metrics

The simulation tracks comprehensive business metrics:

- 💰 **Real-time Profit**: Live P&L calculations
- 😤 **Customer Satisfaction**: Frustration and complaint tracking
- 📦 **Inventory Efficiency**: Stock level optimization
- ⚡ **Production Rate**: Items produced vs. sold analysis
- 🕐 **Service Time**: Customer wait time analytics

## 🎮 Visualization Features

### Production Dashboard
- **Live Bar Charts**: Production vs. sales for all product types
- **Color-coded Products**: Visual distinction between item categories
- **Real-time Updates**: 1-second refresh rate for live monitoring

### Inventory Management
- **Stock Level Bars**: Current inventory quantities
- **Threshold Indicators**: Visual warnings for low stock
- **Material Tracking**: 7 different raw material types
- **Supply Chain Status**: Purchase recommendation system

### Business Intelligence
- **Profit Tracking**: Live financial performance
- **Customer Metrics**: Satisfaction and service quality
- **Time Management**: Simulation progress and elapsed time
- **Threshold Monitoring**: Business goal achievement tracking

## 🔧 Development & Debugging

### Build Options
```bash
# Debug build with detailed logging
make CFLAGS="-Wall -g -DDEBUG -I/usr/include"

# Clean build environment
make clean

# Run with custom configuration
./bin/bakery_simulation path/to/custom_config.txt
```

### Debugging Tips
- Monitor process creation in console output
- Check IPC resource allocation messages
- Watch for inventory threshold warnings
- Observe customer satisfaction trends

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. **🐛 Bug Reports**: Found an issue? Open a detailed bug report
2. **✨ Feature Requests**: Have ideas? We'd love to hear them
3. **🔧 Code Contributions**: Fork, develop, and submit pull requests
4. **📚 Documentation**: Help improve our documentation
5. **🧪 Testing**: Help us test on different platforms

### Development Setup
```bash
git clone https://github.com/HasanQarmash/ipc-bakery-management.git
cd ipc-bakery-management
make clean && make
```

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **POSIX IPC**: For robust inter-process communication
- **OpenGL/GLUT**: For exceptional graphics capabilities  
- **GNU Make**: For efficient build management
- **The C Community**: For continuous language evolution

## 📞 Support & Contact

- 📧 **Email**: HasanQarmash@gmail.com
- 💬 **Discussions**: Use GitHub Discussions for questions
- 🐛 **Issues**: Report bugs via GitHub Issues
- 📖 **Wiki**: Check our Wiki for detailed documentation

---

<div align="center">

**⭐ Star this repository if you found it helpful! ⭐**

*Built with ❤️ using C, OpenGL, and POSIX IPC*

![Bakery Simulation Demo](https://via.placeholder.com/600x300/4CAF50/FFFFFF?text=Real-Time+Bakery+Simulation)

</div>
