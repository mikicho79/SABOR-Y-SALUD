```jsx
import React, { useState } from 'react';
import { Home, Utensils, Newspaper, Users, Search, Calendar, Clock, ChefHat, Leaf, Baby, CalendarDays } from 'lucide-react';

const App = () => {
  const [activeSection, setActiveSection] = useState('home');

  // Mock data for recipes - updated weekly
  const recipes = [
    {
      id: 1,
      title: "Smoothie de Frutas del Bosque",
      description: "Desayuno rico en antioxidantes con frutos rojos, yogur griego y miel natural",
      time: "5 min",
      difficulty: "Fácil",
      image: "https://placehold.co/400x250/8b5cf6/ffffff?text=Smoothie+Frutas",
      tags: ["desayuno", "antioxidantes", "rápido"],
      week: "Semana del 24-30 Nov"
    },
    {
      id: 2,
      title: "Albóndigas de Quinoa y Verduras",
      description: "Fuente de proteína vegetal perfecta para niños, con zanahoria, espinaca y quinoa",
      time: "35 min",
      difficulty: "Media",
      image: "https://placehold.co/400x250/10b981/ffffff?text=Albóndigas+Quinoa",
      tags: ["proteína", "vegetal", "infantil"],
      week: "Semana del 24-30 Nov"
    },
    {
      id: 3,
      title: "Tarta de Manzana Sin Azúcar",
      description: "Postre saludable endulzado con dátiles y canela, ideal para toda la familia",
      time: "50 min",
      difficulty: "Media",
      image: "https://placehold.co/400x250/f59e0b/ffffff?text=Tarta+Manzana",
      tags: ["postre", "sin+azúcar", "fibra"],
      week: "Semana del 24-30 Nov"
    }
  ];

  // Mock data for news - updated weekly
  const news = [
    {
      id: 1,
      title: "Estudio revela beneficios del omega-3 en el rendimiento escolar",
      excerpt: "Investigación publicada esta semana demuestra que el consumo regular de ácidos grasos omega-3 mejora la concentración y memoria en niños escolares.",
      date: "26 Nov 2025",
      image: "https://placehold.co/300x200/3b82f6/ffffff?text=Omega-3+Estudio",
      week: "Actualizado esta semana"
    },
    {
      id: 2,
      title: "Nuevas recomendaciones para la introducción de alimentos alérgenos",
      excerpt: "Expertos actualizan las guías para introducir cacahuetes y huevos en la dieta infantil de forma segura y preventiva.",
      date: "24 Nov 2025",
      image: "https://placehold.co/300x200/ef4444/ffffff?text=Alimentos+Alérgenos",
      week: "Actualizado esta semana"
    },
    {
      id: 3,
      title: "Cómo combatir la deshidratación en niños durante el verano",
      excerpt: "Consejos prácticos para mantener a los niños bien hidratados en los meses más calurosos del año.",
      date: "22 Nov 2025",
      image: "https://placehold.co/300x200/06b6d4/ffffff?text=Hidratación+Verano",
      week: "Actualizado esta semana"
    }
  ];

  // Mock data for nutrition info
  const nutritionTips = [
    {
      title: "Desayuno equilibrado",
      description: "Incluir proteína, fibra y grasas saludables en el desayuno mejora el rendimiento escolar.",
      icon: "🥣"
    },
    {
      title: "Meriendas inteligentes",
      description: "Frutas frescas, frutos secos sin sal o yogur natural son las mejores opciones para entre comidas.",
      icon: "🍎"
    },
    {
      title: "Hidratación constante",
      description: "Ofrecer agua regularmente, especialmente antes, durante y después de la actividad física.",
      icon: "💧"
    },
    {
      title: "Comidas en familia",
      description: "Comer juntos fomenta hábitos alimenticios saludables y mejora la relación con la comida.",
      icon: "👨‍👩‍👧‍👦"
    }
  ];

  const Navigation = () => (
    <nav className="bg-emerald-700 text-white shadow-lg sticky top-0 z-50">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="flex justify-between items-center h-16">
          <div className="flex items-center space-x-2">
            <Leaf className="h-8 w-8 text-emerald-200" />
            <span className="text-xl font-bold">Sabor y Salud</span>
          </div>
          <div className="hidden md:flex space-x-6">
            <button 
              onClick={() => setActiveSection('home')}
              className={`flex items-center space-x-1 px-3 py-2 rounded-md text-sm font-medium transition-colors ${
                activeSection === 'home' ? 'bg-emerald-600' : 'hover:bg-emerald-600'
              }`}
            >
              <Home className="h-4 w-4" />
              <span>Inicio</span>
            </button>
            <button 
              onClick={() => setActiveSection('nutrition')}
              className={`flex items-center space-x-1 px-3 py-2 rounded-md text-sm font-medium transition-colors ${
                activeSection === 'nutrition' ? 'bg-emerald-600' : 'hover:bg-emerald-600'
              }`}
            >
              <Users className="h-4 w-4" />
              <span>Nutrición Infantil</span>
            </button>
            <button 
              onClick={() => setActiveSection('recipes')}
              className={`flex items-center space-x-1 px-3 py-2 rounded-md text-sm font-medium transition-colors ${
                activeSection === 'recipes' ? 'bg-emerald-600' : 'hover:bg-emerald-600'
              }`}
            >
              <Utensils className="h-4 w-4" />
              <span>Recetas Saludables</span>
            </button>
            <button 
              onClick={() => setActiveSection('news')}
              className={`flex items-center space-x-1 px-3 py-2 rounded-md text-sm font-medium transition-colors ${
                activeSection === 'news' ? 'bg-emerald-600' : 'hover:bg-emerald-600'
              }`}
            >
              <Newspaper className="h-4 w-4" />
              <span>Noticias</span>
            </button>
          </div>
          <div className="md:hidden">
            <button className="p-2 rounded-md hover:bg-emerald-600">
              <ChefHat className="h-6 w-6" />
            </button>
          </div>
        </div>
      </div>
    </nav>
  );

  const HeroSection = () => (
    <div className="bg-gradient-to-r from-emerald-600 to-teal-600 text-white py-20">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
        <h1 className="text-4xl md:text-6xl font-bold mb-6">Sabor y Salud</h1>
        <p className="text-xl md:text-2xl mb-8 max-w-3xl mx-auto">
          Información actualizada semanalmente sobre nutrición infantil, recetas saludables y noticias especializadas
        </p>
        <div className="flex items-center justify-center mb-6">
          <CalendarDays className="h-5 w-5 mr-2" />
          <span className="text-emerald-100 font-medium">Actualizado semanalmente</span>
        </div>
        <div className="flex flex-col sm:flex-row gap-4 justify-center">
          <button 
            onClick={() => setActiveSection('nutrition')}
            className="bg-white text-emerald-700 px-8 py-3 rounded-full font-semibold hover:bg-emerald-50 transition-colors"
          >
            Guías Nutricionales
          </button>
          <button 
            onClick={() => setActiveSection('recipes')}
            className="border-2 border-white text-white px-8 py-3 rounded-full font-semibold hover:bg-white/10 transition-colors"
          >
            Recetas de la Semana
          </button>
        </div>
      </div>
    </div>
  );

  const HomeSection = () => (
    <div className="py-16 bg-gray-50">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12">
          <h2 className="text-3xl font-bold mb-4">Contenido Actualizado Semanalmente</h2>
          <p className="text-gray-600 max-w-2xl mx-auto">
            En Sabor y Salud, te proporcionamos información fresca y actualizada cada semana sobre nutrición infantil, 
            nuevas recetas y las últimas noticias del sector.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-3 gap-8 mb-16">
          <div className="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow border-l-4 border-emerald-500">
            <div className="w-12 h-12 bg-emerald-100 rounded-lg flex items-center justify-center mb-4">
              <Users className="h-6 w-6 text-emerald-600" />
            </div>
            <h3 className="text-xl font-semibold mb-2">Nutrición Infantil</h3>
            <p className="text-gray-600 mb-3">Guías actualizadas semanalmente con recomendaciones basadas en las últimas investigaciones científicas.</p>
            <div className="flex items-center text-sm text-emerald-600 font-medium">
              <CalendarDays className="h-4 w-4 mr-1" />
              Actualización semanal
            </div>
          </div>
          <div className="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow border-l-4 border-amber-500">
            <div className="w-12 h-12 bg-amber-100 rounded-lg flex items-center justify-center mb-4">
              <Utensils className="h-6 w-6 text-amber-600" />
            </div>
            <h3 className="text-xl font-semibold mb-2">Recetas Saludables</h3>
            <p className="text-gray-600 mb-3">Nuevas recetas cada semana, diseñadas específicamente para el paladar infantil y ricas en nutrientes.</p>
            <div className="flex items-center text-sm text-amber-600 font-medium">
              <CalendarDays className="h-4 w-4 mr-1" />
              Nuevas recetas semanales
            </div>
          </div>
          <div className="bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-shadow border-l-4 border-blue-500">
            <div className="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-4">
              <Newspaper className="h-6 w-6 text-blue-600" />
            </div>
            <h3 className="text-xl font-semibold mb-2">Noticias Actualizadas</h3>
            <p className="text-gray-600 mb-3">Reportajes semanales sobre los últimos descubrimientos y tendencias en nutrición infantil.</p>
            <div className="flex items-center text-sm text-blue-600 font-medium">
              <CalendarDays className="h-4 w-4 mr-1" />
              Noticias de la semana
            </div>
          </div>
        </div>

        <div className="text-center">
          <h2 className="text-3xl font-bold mb-8">Consejos Nutricionales Esenciales</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            {nutritionTips.map((tip, index) => (
              <div key={index} className="bg-white p-6 rounded-xl shadow-md border border-gray-200">
                <div className="text-3xl mb-3">{tip.icon}</div>
                <h3 className="font-semibold mb-2">{tip.title}</h3>
                <p className="text-gray-600 text-sm">{tip.description}</p>
              </div>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  const NutritionSection = () => (
    <div className="py-16">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12">
          <div className="flex items-center justify-center mb-4">
            <Baby className="h-8 w-8 text-emerald-600 mr-2" />
            <h2 className="text-3xl font-bold">Nutrición Infantil</h2>
          </div>
          <div className="flex items-center justify-center mb-6">
            <CalendarDays className="h-5 w-5 mr-2 text-emerald-600" />
            <span className="text-emerald-600 font-medium">Actualizado cada semana</span>
          </div>
          <p className="text-gray-600 max-w-3xl mx-auto">
            La alimentación adecuada durante la infancia es fundamental para el crecimiento, desarrollo y prevención de enfermedades. 
            Aquí encontrarás información actualizada semanalmente basada en evidencia científica para guiar la nutrición de tus hijos.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-2 gap-12">
          <div className="bg-gradient-to-br from-emerald-50 to-teal-50 p-8 rounded-2xl border border-emerald-100">
            <h3 className="text-2xl font-bold mb-6 text-emerald-800">Grupos de Edad</h3>
            <div className="space-y-4">
              <div className="bg-white p-4 rounded-lg shadow-sm border border-emerald-100">
                <h4 className="font-semibold text-lg">0-12 meses</h4>
                <p className="text-gray-600 text-sm mt-2">Lactancia exclusiva hasta los 6 meses, introducción gradual de alimentos sólidos.</p>
                <div className="mt-2 text-xs text-emerald-600 font-medium">Actualizado esta semana</div>
              </div>
              <div className="bg-white p-4 rounded-lg shadow-sm border border-emerald-100">
                <h4 className="font-semibold text-lg">1-3 años</h4>
                <p className="text-gray-600 text-sm mt-2">Amplia variedad de alimentos, porciones adecuadas, límites de azúcar y sal.</p>
                <div className="mt-2 text-xs text-emerald-600 font-medium">Actualizado esta semana</div>
              </div>
              <div className="bg-white p-4 rounded-lg shadow-sm border border-emerald-100">
                <h4 className="font-semibold text-lg">4-12 años</h4>
                <p className="text-gray-600 text-sm mt-2">Equilibrio nutricional para soportar el crecimiento y actividad escolar.</p>
                <div className="mt-2 text-xs text-emerald-600 font-medium">Actualizado esta semana</div>
              </div>
            </div>
          </div>

          <div className="bg-gradient-to-br from-amber-50 to-orange-50 p-8 rounded-2xl border border-amber-100">
            <h3 className="text-2xl font-bold mb-6 text-amber-800">Nutrientes Esenciales por Semana</h3>
            <div className="space-y-4">
              <div className="flex items-start space-x-4">
                <div className="w-12 h-12 bg-amber-100 rounded-full flex items-center justify-center flex-shrink-0">
                  <span className="font-bold text-amber-700 text-lg">Ca</span>
                </div>
                <div>
                  <h4 className="font-semibold">Calcio - Esta Semana</h4>
                  <p className="text-gray-600 text-sm mt-1">Para huesos y dientes fuertes. Fuentes: lácteos, verduras de hoja verde, almendras.</p>
                </div>
              </div>
              <div className="flex items-start space-x-4">
                <div className="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0">
                  <span className="font-bold text-blue-700 text-lg">Fe</span>
                </div>
                <div>
                  <h4 className="font-semibold">Hierro - Esta Semana</h4>
                  <p className="text-gray-600 text-sm mt-1">Prevención de anemia. Fuentes: carnes magras, legumbres, espinacas, frutos secos.</p>
                </div>
              </div>
              <div className="flex items-start space-x-4">
                <div className="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center flex-shrink-0">
                  <span className="font-bold text-purple-700 text-lg">Om</span>
                </div>
                <div>
                  <h4 className="font-semibold">Omega-3 - Esta Semana</h4>
                  <p className="text-gray-600 text-sm mt-1">Desarrollo cerebral óptimo. Fuentes: pescado azul, nueces, semillas de chía, aceite de linaza.</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  );

  const RecipesSection = () => (
    <div className="py-16 bg-gray-50">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12">
          <h2 className="text-3xl font-bold mb-4">Recetas Saludables de la Semana</h2>
          <div className="flex items-center justify-center mb-4">
            <CalendarDays className="h-5 w-5 mr-2 text-emerald-600" />
            <span className="text-emerald-600 font-medium">Nuevas recetas cada semana</span>
          </div>
          <p className="text-gray-600 max-w-2xl mx-auto">
            Recetas nutritivas, deliciosas y fáciles de preparar que encantarán a los más pequeños de la casa. 
            Actualizadas semanalmente con nuevas ideas y variaciones.
          </p>
        </div>

        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          {recipes.map((recipe) => (
            <div key={recipe.id} className="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-xl transition-shadow border border-gray-100">
              <div className="relative">
                <img 
                  src={recipe.image} 
                  alt={recipe.title}
                  className="w-full h-48 object-cover"
                />
                <div className="absolute top-3 right-3 bg-emerald-600 text-white text-xs font-semibold px-2 py-1 rounded-full">
                  {recipe.week}
                </div>
              </div>
              <div className="p-6">
                <h3 className="text-xl font-bold mb-2">{recipe.title}</h3>
                <p className="text-gray-600 mb-4">{recipe.description}</p>
                <div className="flex items-center justify-between mb-4">
                  <div className="flex items-center space-x-4 text-sm text-gray-500">
                    <div className="flex items-center space-x-1">
                      <Clock className="h-4 w-4" />
                      <span>{recipe.time}</span>
                    </div>
                    <span className="capitalize">{recipe.difficulty}</span>
                  </div>
                </div>
                <div className="flex flex-wrap gap-2">
                  {recipe.tags.map((tag, index) => (
                    <span key={index} className="px-2 py-1 bg-emerald-100 text-emerald-800 text-xs rounded-full">
                      {tag.replace('+', ' ')}
                    </span>
                  ))}
                </div>
              </div>
            </div>
          ))}
        </div>
        
        <div className="text-center mt-12">
          <button className="bg-emerald-600 text-white px-8 py-3 rounded-full font-semibold hover:bg-emerald-700 transition-colors">
            Ver todas las recetas de la semana
          </button>
        </div>
      </div>
    </div>
  );

  const NewsSection = () => (
    <div className="py-16">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12">
          <h2 className="text-3xl font-bold mb-4">Noticias de Nutrición Infantil</h2>
          <div className="flex items-center justify-center mb-4">
            <CalendarDays className="h-5 w-5 mr-2 text-emerald-600" />
            <span className="text-emerald-600 font-medium">Actualizadas semanalmente</span>
          </div>
          <p className="text-gray-600 max-w-2xl mx-auto">
            Mantente informado sobre las últimas investigaciones, guías y recomendaciones en nutrición infantil. 
            Nuevos artículos cada semana con información relevante y basada en evidencia.
          </p>
        </div>

        <div className="grid grid-cols-1 lg:grid-cols-3 gap-8">
          {news.map((article) => (
            <div key={article.id} className="bg-white rounded-2xl shadow-lg overflow-hidden hover:shadow-xl transition-shadow border border-gray-100">
              <div className="relative">
                <img 
                  src={article.image} 
                  alt={article.title}
                  className="w-full h-48 object-cover"
                />
                <div className="absolute top-3 right-3 bg-blue-600 text-white text-xs font-semibold px-2 py-1 rounded-full">
                  {article.week}
                </div>
              </div>
              <div className="p-6">
                <div className="flex items-center text-sm text-gray-500 mb-3">
                  <Calendar className="h-4 w-4 mr-1" />
                  {article.date}
                </div>
                <h3 className="text-xl font-bold mb-3">{article.title}</h3>
                <p className="text-gray-600 mb-4">{article.excerpt}</p>
                <button className="text-emerald-600 font-semibold hover:text-emerald-700 transition-colors flex items-center">
                  Leer más →
                </button>
              </div>
            </div>
          ))}
        </div>
        
        <div className="text-center mt-12">
          <button className="border-2 border-emerald-600 text-emerald-600 px-8 py-3 rounded-full font-semibold hover:bg-emerald-600 hover:text-white transition-colors">
            Ver todas las noticias de la semana
          </button>
        </div>
      </div>
    </div>
  );

  const SearchBar = () => (
    <div className="max-w-2xl mx-auto px-4 sm:px-6 lg:px-8 mb-8">
      <div className="relative">
        <Search className="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400 h-5 w-5" />
        <input
          type="text"
          placeholder="Buscar recetas, noticias o consejos..."
          className="w-full pl-10 pr-4 py-3 border border-gray-300 rounded-full focus:outline-none focus:ring-2 focus:ring-emerald-500 focus:border-transparent"
        />
      </div>
    </div>
  );

  const Footer = () => (
    <footer className="bg-gray-900 text-white py-12">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="grid grid-cols-1 md:grid-cols-4 gap-8">
          <div className="col-span-1 md:col-span-2">
            <div className="flex items-center space-x-2 mb-4">
              <Leaf className="h-8 w-8 text-emerald-400" />
              <span className="text-2xl font-bold">Sabor y Salud</span>
            </div>
            <p className="text-gray-400 mb-4">
              Tu guía confiable para la nutrición infantil saludable. Información actualizada semanalmente 
              basada en evidencia científica para ayudarte a criar niños sanos y felices.
            </p>
            <div className="flex space-x-4">
              <div className="w-10 h-10 bg-emerald-600 rounded-full flex items-center justify-center">
                <span className="font-bold">f</span>
              </div>
              <div className="w-10 h-10 bg-emerald-600 rounded-full flex items-center justify-center">
                <span className="font-bold">t</span>
              </div>
              <div className="w-10 h-10 bg-emerald-600 rounded-full flex items-center justify-center">
                <span className="font-bold">ig</span>
              </div>
            </div>
          </div>
          <div>
            <h3 className="text-lg font-semibold mb-4">Secciones</h3>
            <ul className="space-y-2 text-gray-400">
              <li><button onClick={() => setActiveSection('nutrition')} className="hover:text-white transition-colors">Nutrición Infantil</button></li>
              <li><button onClick={() => setActiveSection('recipes')} className="hover:text-white transition-colors">Recetas Saludables</button></li>
              <li><button onClick={() => setActiveSection('news')} className="hover:text-white transition-colors">Noticias</button></li>
            </ul>
          </div>
          <div>
            <h3 className="text-lg font-semibold mb-4">Actualización</h3>
            <ul className="space-y-2 text-gray-400">
              <li>Contenido semanal</li>
              <li>Lunes de cada semana</li>
              <li>info@saborysalud.com</li>
            </ul>
          </div>
        </div>
        <div className="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
          <p>&copy; 2025 Sabor y Salud. Todos los derechos reservados. Contenido actualizado semanalmente.</p>
        </div>
      </div>
    </footer>
  );

  return (
    <div className="min-h-screen bg-white">
      <Navigation />
      <SearchBar />
      
      {activeSection === 'home' && (
        <>
          <HeroSection />
          <HomeSection />
        </>
      )}
      
      {activeSection === 'nutrition' && <NutritionSection />}
      {activeSection === 'recipes' && <RecipesSection />}
      {activeSection === 'news' && <NewsSection />}
      
      <Footer />
    </div>
  );
};

export default App;
```
