

# 🎮 Catálogo Dinámico de Videojuegos — Scraping Automatizado

Este proyecto genera automáticamente un catálogo completo de videojuegos utilizando *web scraping* y lo muestra en una página web interactiva publicada con **GitHub Pages**.
El objetivo es crear un proyecto profesional para portafolio, útil para añadir en el **Currículum Vitae (CV)** o en **LinkedIn**.

---

## 📌 ¿Qué hace este proyecto?

El sistema tiene **dos partes principales**:

---

## 🔹 1. Scraper automático (Python)

Un script avanzado que recopila **210 videojuegos reales** desde:

* **Steam **
* **GOG **
* **Green Man Gaming **
  

El scraper obtiene datos reales como:

* Nombre del juego
* Precio regular
* Precio con descuento
* Porcentaje de descuento
* Plataforma (PC, Xbox, PlayStation)
* Portada del juego
* Duración estimada (*HowLongToBeat*)
* Calificación estilo Metacritic 
* URL original del producto

### ✔ Características del scraper

* Utiliza tres niveles de paralelismo para cada tienda
* Evita juegos repetidos entre las 3 tiendas.
* Todo se guarda automáticamente en:

  * `results.json`
  * `results.csv`
* Cada ejecución termina con un **git push automático** para actualizar los datos en GitHub.
* Corre **cada 3 minutos** en un ciclo infinito.

---

## 🔹 2. Página web dinámica (HTML + JavaScript)

Publicada mediante **GitHub Pages**, carga los datos directamente desde `results.json`.

Incluye:

### ✔ Filtros

* Tienda
* Formato (Digital / Físico)
* Plataforma (PC, PlayStation, Xbox)
* Buscador por nombre

### ✔ Ordenamiento

* Nombre
* Precio
* Descuento
* Puntaje

### ✔ Vista de catálogo

* Tarjetas estilo tienda real
* Portada del juego
* Precio, ahorro, rating y duración
* Botón para ver detalle del juego
* Interfaz oscura moderna

### ✔ Vista de Detalle

Incluye versión ampliada de:

* Nombre
* Imagen
* Precio
* Duración
* Distribución
* Plataforma
* Enlace a la tienda original

---

## ⚙ Tecnologías utilizadas

### Backend / Scraper

* Python 3
* aiohttp
* aiofiles
* BeautifulSoup4
* lxml
* Expresiones regulares
* subprocess (para git)

### Frontend

* HTML5
* CSS
* JavaScript Vanilla
* GitHub Pages (hosting)

---

## 🧠 ¿Cómo funciona internamente?

### 1. **Seeders**

Recolectan cientos de URLs reales desde:

* Steam 
* GOG 
* Green Man Gaming

### 2. **Scraping individual**

Para cada juego se analiza:

* Precio
* Descuento
* Imagen
* Plataforma
* Nombre limpio
* Duración aproximada
* Calificación de Metacritic

### 3. **Eliminación de duplicados**

Los nombres se normalizan (sin ™, -, :, ®…)
Así, un juego **no se repite** entre tiendas.

### 4. **Fallback inteligente**

Si un juego no tiene datos reales:

* se descarta


### 5. **Auto Git Push**

Cuando termina:

```
git add results.json results.csv
git commit -m "Actualizar datos..."
git push
```

---

## 🚀 ¿Cómo ejecutar el scraper?

### 1. Instalar dependencias:

```
pip install aiohttp aiofiles beautifulsoup4 lxml
```

### 2. Ejecutar el scraper:

```
datos.py
```

### 3. El scraper se repetirá solo cada 3 minutos.

---

## 🌐 Publicar la web con GitHub Pages

1. Sube `index.html` a la raíz del repositorio
2. Ve a **Settings → Pages**
3. Donde dice *Source*, selecciona:

```
Branch: main
Folder: / (root)
```

4. Guarda cambios
5. La página aparecerá en:

```
https://danny7w7-coder.github.io/proyecto-multicore-web/
```

---

## 👤 Autores del proyecto

**Valeria Rojas Barrantes**
Estudiante de Ingeniería en Computadores
Instituto Tecnológico de Costa Rica (TEC)

**Dylan Méndez Zamora**
Estudiante de Ingeniería en Computadores
Instituto Tecnológico de Costa Rica (TEC)

**Danny González Molina**
Estudiante de Ingeniería en Computadores
Instituto Tecnológico de Costa Rica (TEC)



