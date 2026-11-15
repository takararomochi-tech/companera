
plugins {
    id 'java-library'
    id 'net.neoforged.moddev' version '2.0.+'
}

group = 'com.companera'
version = '1.0.0'

base { archivesName = 'companera' }

java.toolchain.languageVersion = JavaLanguageVersion.of(25)

repositories {
    mavenCentral()
    maven { url = 'https://maven.neoforged.net/releases' }
}

neoForge {
    version = '26.3.0.103'
    runs {
        client { client() }
    }
    mods {
        companera { sourceSet sourceSets.main }
    }
}

org.gradle.jvmargs=-Xmx2G
org.gradle.daemon=false

MOD "COMPAÑERA IA" - NeoForge 26.3.0.103 (solo el mod)
=======================================================
Este zip es el PROYECTO del mod listo para compilar. No incluye el .jar porque yo no
puedo compilarlo desde aquí (sin JDK 25 ni acceso a las librerías de NeoForge).

--- OPCIÓN A: compilar en tu PC ---
1. Instala JDK 25 y Gradle 9.x (o abre la carpeta en IntelliJ IDEA, que lo hace solo).
2. En esta carpeta:   gradle build
3. El mod queda en  build/libs/companera-1.0.0.jar
4. Prism Launcher -> tu instancia -> Mods -> Añadir archivo -> ese .jar.

--- OPCIÓN B: subirlo a GitHub y que lo compile GitHub (sin instalar nada) ---
1. Crea un repositorio nuevo en github.com y sube TODO el contenido de esta carpeta
   (incluida la carpeta oculta .github).
2. Entra a la pestaña "Actions" -> "Compilar mod" -> espera a que termine (palomita verde).
3. Abre esa ejecución -> abajo en "Artifacts" descarga "companera-mod" -> dentro está el .jar.

--- Si falla la compilación ---
Es una versión muy nueva y no pude probar el código. Copia el error completo y pásamelo.
Lo más frágil está en src/main/java/com/companera/Compat.java y CompanionRenderer.java.
Si el error es del plugin de Gradle (build.gradle), puede que cambie el número de versión
de 'net.neoforged.moddev': generando un proyecto nuevo en el Mod Generator de NeoForged
verás el que corresponde a 26.3.

--- Recuerda ---
El mod por sí solo no habla ni piensa: necesita la app (Companera_IA.zip -> carpeta app)
abierta mientras juegas.

pluginManagement {
    repositories {
        gradlePluginPortal()
        maven { url = 'https://maven.neoforged.net/releases' }
    }
}
rootProject.name = 'companera'
