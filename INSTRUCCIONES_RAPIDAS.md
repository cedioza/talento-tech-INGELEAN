# 🚀 Instrucciones Rápidas - INGE LEAN Chatbot (Puerto 3001)

## ⚡ Inicio Rápido

### 1. Instalar dependencias (solo la primera vez)
```bash
npm run install:all
```

### 2. Ejecutar en desarrollo
```bash
npm run dev
```

### 3. Acceder a la aplicación
- **Frontend (Chatbot)**: http://localhost:5173
- **Backend API**: http://localhost:3001
- **Health Check**: http://localhost:3001/health

---

## 🔧 Comandos Disponibles

| Comando | Descripción |
|---------|-------------|
| `npm run dev` | Ejecuta frontend y backend simultáneamente |
| `npm run dev:backend` | Solo el backend (puerto 3001) |
| `npm run dev:frontend` | Solo el frontend (puerto 5173) |
| `npm run test:api` | Verificar si el backend está funcionando |
| `npm start` | Ejecutar en modo producción |

---

## 📊 Funcionalidades Incluidas

### ✅ Chatbot Inteligente
- Respuestas automáticas sobre servicios de INGE LEAN
- Sistema de sugerencias rápidas
- Interfaz estilo chat moderno

### ✅ Base de Conocimiento
- ¿Qué es INGE LEAN?
- Servicios de consultoría
- Lean Manufacturing
- Información de contacto

### ✅ Métricas y Trazabilidad
- Todas las conversaciones se guardan en SQLite
- Tiempo de respuesta registrado
- Sistema de satisfacción del usuario

---

## 🔍 Verificar que funciona

1. **Backend funcionando**: http://localhost:3001/health
2. **Frontend funcionando**: http://localhost:5173
3. **Probar API**: http://localhost:3001/api/chat/suggestions

---

## 🚨 Solución de Problemas

### Backend no inicia
```bash
# Verificar que el puerto 3001 esté libre
netstat -an | find "3001"

# Reinstalar dependencias del backend
cd backend
rm -rf node_modules
npm install
```

### Frontend no conecta
- Verificar que el backend esté corriendo en puerto 3001
- Revisar la consola del navegador para errores

### Error de permisos
```bash
# En Windows, ejecutar como administrador
# En Linux/Mac:
sudo npm run dev
```

---

**🎯 Todo listo para usar! El chatbot está configurado para funcionar en el puerto 3001** 