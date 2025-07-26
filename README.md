# 🤖 INGE LEAN Chatbot Inteligente

[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![Vue.js](https://img.shields.io/badge/Vue.js-3.3+-blue.svg)](https://vuejs.org/)
[![Express](https://img.shields.io/badge/Express-4.18+-red.svg)](https://expressjs.com/)
[![Mistral AI](https://img.shields.io/badge/Mistral%20AI-small-orange.svg)](https://mistral.ai/)
[![SQLite](https://img.shields.io/badge/SQLite-3.0+-lightblue.svg)](https://sqlite.org/)


##Participantes


Estefany Romero.
Cristian Dioza.
Davin Chavarría
  
Sistema de chatbot inteligente híbrido para **INGE LEAN** que combina respuestas basadas en FAQs con Inteligencia Artificial (Mistral AI) para brindar soporte automatizado 24/7 a clientes y prospectos.

## 🎯 **Características Principales**

### 🤖 **Sistema Híbrido Inteligente**
- **FAQs Locales**: Respuestas rápidas y precisas para consultas frecuentes
- **Mistral AI**: Fallback inteligente usando `mistral-small` para consultas complejas
- **Validación de Contexto**: Solo responde preguntas relacionadas con INGE LEAN
- **Procesamiento NLP**: Normalización de texto, manejo de acentos y sinónimos

### 📊 **Dashboard y Métricas**
- **Métricas en Tiempo Real**: Monitoreo de conversaciones activas
- **Analytics Avanzados**: Estadísticas de uso, preguntas frecuentes y satisfacción
- **Exportación de Datos**: Reportes y métricas descargables
- **Monitoreo de Performance**: Tiempos de respuesta y disponibilidad

### 🌐 **Interfaz Moderna**
- **Vue.js 3**: SPA moderna y responsiva
- **Tailwind CSS**: Diseño corporativo de INGE LEAN
- **Componentes Modulares**: Arquitectura escalable y mantenible
- **Soporte Móvil**: Optimizado para dispositivos móviles

### 🔧 **Testing Integrado**
- **Pruebas Automatizadas**: Validación de FAQs, API de Mistral AI y performance
- **Feedback Visual**: Indicadores de estado y tiempo de respuesta
- **Ambiente de Pruebas**: Testing completo antes de producción

## 🏗️ **Arquitectura del Sistema**

```
frontend/
├── src/
│   ├── views/
│   │   ├── Home.vue           # 🏠 Página principal del chatbot
│   │   ├── Dashboard.vue      # 📊 Panel de métricas
│   │   ├── Requisitos.vue     # 📋 Documentación técnica
│   │   ├── Testing.vue        # 🧪 Interface de pruebas
│   │   └── IngeLeanHome.vue   # 🌐 Clon de ingelean.com
│   ├── components/
│   │   └── [Componentes Vue]
│   ├── main.js                # ⚙️ Configuración de rutas
│   └── style.css              # 🎨 Estilos globales
├── vite.config.js             # ⚡ Configuración Vite
├── tailwind.config.js         # 🎨 Configuración Tailwind
└── package.json               # 📦 Dependencias frontend
```

sequenceDiagram
    participant U as 👤 Usuario
    participant F as 🌐 Frontend
    participant B as 🚀 Backend
    participant H as 🔀 Híbrido
    participant FAQ as 📋 FAQ
    participant AI as 🤖 IA


## 🚀 **Tecnologías Utilizadas**

### **Backend**
- **Node.js** (18+) - Runtime de JavaScript
- **Express.js** (4.18+) - Framework web minimalista
- **SQLite** (3.0+) - Base de datos local para persistencia
- **Mistral AI API** - Modelo `mistral-small` para IA conversacional
- **Helmet** - Seguridad HTTP
- **Rate Limiting** - Control de tráfico
- **Morgan** - Logging de requests
- **UUID** - Generación de IDs únicos

### **Frontend**
- **Vue.js** (3.3+) - Framework progresivo
- **Vue Router** (4.2+) - Enrutamiento SPA
- **Tailwind CSS** (3.0+) - Framework de utilidades CSS
- **Vite** (5.0+) - Build tool y desarrollo
- **Axios** (1.6+) - Cliente HTTP
- **PostCSS** - Procesamiento CSS

### **Base de Conocimiento**
- **14 FAQs Especializadas** - Cobertura completa de servicios INGE LEAN
- **Algoritmo NLP Custom** - Procesamiento de lenguaje natural optimizado
- **Validación de Contexto** - Filtros para mantener conversaciones relevantes
- **Respuestas Estructuradas** - Formato markdown para mejor UX

## 📦 **Instalación y Configuración**

### **Prerrequisitos**
- Node.js 18+ instalado
- npm o yarn como package manager
- Puerto 3001 (backend) y 5173 (frontend) disponibles

### **1. Clonar el Repositorio**
```bash
git clone <repository-url>
cd inge-lean-chatbot
```

### **2. Instalación de Dependencias**
```bash
# Instalar todas las dependencias (raíz, backend y frontend)
npm run install:all

# O instalar manualmente
npm install
cd backend && npm install
cd ../frontend && npm install
```

### **3. Configuración del Entorno**

#### **Backend (.env opcional)**
```env
PORT=3001
MISTRAL_API_KEY=xw6omhuYjjwrlbLBGx0StAousw8OUtG7
NODE_ENV=development
```

#### **Frontend (vite.config.js)**
- Puerto: 5173
- Proxy API: http://localhost:3001
- Host: 0.0.0.0 (para ngrok)

### **4. Ejecución del Proyecto**

#### **Desarrollo (Recomendado)**
```bash
# Ejecutar backend y frontend simultáneamente
npm run dev
```

#### **Ejecución Separada**
```bash
# Terminal 1: Backend
cd backend
npm run dev

# Terminal 2: Frontend  
cd frontend
npm run dev
```

### **5. Acceso al Sistema**
- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:3001
- **Health Check**: http://localhost:3001/health

## 🌐 **Configuración para ngrok (Opcional)**

Para exposición pública del chatbot:

```bash
# Exponer frontend
ngrok http 5173

# Exponer backend (si es necesario)
ngrok http 3001
```

El sistema ya está configurado para soportar dominios ngrok automáticamente.

## 📱 **Rutas y Funcionalidades**

### **Frontend Routes**
- `/` - **Chatbot Principal**: Interfaz de conversación
- `/dashboard` - **Dashboard**: Métricas y analytics  
- `/requisitos` - **Documentación**: Requisitos técnicos
- `/testing` - **Testing**: Pruebas automatizadas del sistema

### **Backend API Endpoints**
```
POST   /api/chat/message          # Enviar mensaje al chatbot
GET    /api/chat/suggestions      # Obtener sugerencias de chat
POST   /api/chat/mistral          # Interacción directa con Mistral AI
GET    /api/chat/mistral/health   # Estado de Mistral AI

GET    /api/metrics/realtime      # Métricas en tiempo real
GET    /api/metrics/dashboard     # Datos del dashboard
POST   /api/feedback              # Enviar feedback de usuario

GET    /health                    # Health check del servidor
```

## 🧪 **Testing y Validación**

### **Testing Automatizado**
El sistema incluye un módulo de testing integrado (`/testing`) que valida:

- ✅ **Conectividad Backend**: Health check y latencia
- ✅ **FAQs Locales**: Cobertura y precisión de respuestas
- ✅ **Mistral AI**: Conectividad y calidad de respuestas
- ✅ **Performance**: Tiempos de respuesta < 2 segundos
- ✅ **Concurrencia**: Manejo de múltiples usuarios

### **Validación Manual**
```bash
# Health check
curl http://localhost:3001/health

# Test FAQ
curl -X POST http://localhost:3001/api/chat/message \
  -H "Content-Type: application/json" \
  -d '{"message": "¿Qué servicios ofrecen?"}'

# Test Mistral AI
curl -X POST http://localhost:3001/api/chat/mistral \
  -H "Content-Type: application/json" \
  -d '{"message": "Información sobre automatización industrial"}'
```

## 🔒 **Seguridad y Configuración**

### **Medidas de Seguridad Implementadas**
- **Helmet**: Headers de seguridad HTTP
- **Rate Limiting**: 100 requests/15min por IP
- **CORS**: Configurado para dominios específicos
- **Validación de Input**: Sanitización de mensajes
- **Trust Proxy**: Configurado para ngrok/proxies

### **Validación de Contexto**
El chatbot incluye un sistema de validación que:
- Solo responde preguntas relacionadas con INGE LEAN
- Rechaza consultas sobre otros temas (deportes, política, etc.)
- Mantiene el foco en servicios de ingeniería

## 📈 **Métricas y Monitoreo**

### **KPIs Tracked**
- **Interacciones Totales**: Número de conversaciones
- **Tiempo de Respuesta**: Latencia promedio < 2s
- **Tasa de Resolución**: % de preguntas respondidas correctamente
- **Satisfacción Usuario**: Rating y feedback
- **Preguntas Frecuentes**: Análisis de patrones
- **Escalaciones**: Derivaciones a soporte humano

### **Dashboard Analytics**
- Gráficos en tiempo real
- Métricas por períodos (día, semana, mes)
- Exportación de reportes
- Monitoreo de salud del sistema

## 🚀 **Despliegue en Producción**

### **Opciones de Despliegue**
1. **Netlify + Heroku**: Frontend en Netlify, Backend en Heroku
2. **Vercel + Railway**: Full-stack serverless
3. **Docker**: Containerización completa
4. **VPS/Cloud**: Servidor dedicado

### **Build para Producción**
```bash
# Build del frontend
cd frontend
npm run build

# El backend se ejecuta directamente
cd backend
npm start
```

## 🤖 **Funcionalidades del Chatbot**

### **FAQs Incluidas**
1. **Saludos** - Bienvenida personalizada
2. **Servicios** - Software, hardware, automatización, IA
3. **Horarios** - Atención y soporte 24/7
4. **Ubicación** - Pereira, Colombia + cobertura internacional
5. **Cotizaciones** - Proceso y contacto
6. **Mantenimiento** - Industrial y remoto
7. **Soluciones a medida** - Desarrollo personalizado
8. **Soporte remoto** - Asistencia mundial
9. **Cobertura** - España, Paraguay, Colombia
10. **Tecnologías** - Industria 4.0, IoT, IA
11. **Contacto** - Email, WhatsApp, web
12. **Empresa** - Información de INGE LEAN
13. **Precios** - Modalidades y cotización
14. **Despedidas** - Cierre amigable

### **Validación Inteligente**
```javascript
// Ejemplo de preguntas que SÍ responde:
"¿Qué servicios ofrecen?"
"¿Cuáles son sus horarios?"
"¿Hacen desarrollo de software?"
"¿Cómo solicito una cotización?"

// Ejemplo de preguntas que RECHAZA:
"¿Quién ganó el partido de fútbol?"
"¿Cómo está el clima?"
"¿Cuál es la capital de Francia?"
```

## 🛠️ **Personalización**

### **Agregar Nuevas FAQs**
1. Editar `backend/data/faqs.js`
2. Agregar nueva entrada en el objeto `FAQS`
3. Definir keywords y response apropiados
4. Reiniciar el servidor

### **Cambiar Modelo de IA**
```javascript
// En backend/services/mistralService.js
this.model = 'mistral-small'; // Actual
// Opciones: mistral-tiny, mistral-small, mistral-medium, mistral-large
```

### **Personalización Visual**
1. Modificar `frontend/tailwind.config.js` para colores
2. Editar componentes en `frontend/src/views/`
3. Actualizar assets en `frontend/public/`

## 📞 **Soporte y Contacto**

- **Empresa**: INGE LEAN
- **Email**: comercial@ingelean.com
- **WhatsApp**: +57 304 326 2538
- **Ubicación**: Pereira, Risaralda, Colombia

## 📄 **Licencia**

Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

---

**Desarrollado con ❤️ para INGE LEAN - Ingeniería especializada a la medida**

🚀 **¿Listo para implementar tu chatbot inteligente? ¡Contáctanos!**

---

Este README actualizado incluye todas las nuevas funcionalidades que hemos implementado:

✅ **Modelo Mistral AI** (`mistral-small`)
✅ **Validación de contexto** para preguntas relacionadas
✅ **Sistema híbrido** FAQ + IA
✅ **Configuración para ngrok**
✅ **Testing automatizado**
✅ **14 FAQs especializadas**
✅ **Navegación simplificada** (sin clon IngeLean)
✅ **Instrucciones completas** de instalación y uso

¿Te parece bien el contenido o quieres que agregue o modifique alguna sección específica? 
