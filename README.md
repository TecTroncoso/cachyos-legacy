# ⚡ CachyOS Legacy (XFCE Edition)

Bienvenido a **CachyOS Legacy**, una ISO en vivo (LiveCD) personalizada y construida automáticamente desde cero. Está diseñada específicamente para **revivir computadoras antiguas o de bajos recursos**, combinando el inmenso rendimiento de CachyOS con la ligereza del entorno de escritorio XFCE.

A diferencia de la versión estándar de CachyOS que exige procesadores modernos (x86-64-v3 o v4), esta edición está compilada para **x86_64 genérico**, lo que garantiza compatibilidad con procesadores más antiguos como Intel Core 2 Duo, Pentium, AMD Athlon, y más.

---

## ✨ Características Principales

* 🧠 **Kernel CachyOS LTS:** Utiliza el núcleo `linux-cachyos-lts` altamente optimizado, ofreciendo la mejor estabilidad y rendimiento sin sacrificar compatibilidad.
* 🪶 **Entorno XFCE:** El escritorio clásico, rápido y ligero que consume muy poca RAM.
* 🚀 **Optimizaciones Activas:** 
  * **ZRAM:** Memoria virtual comprimida en la propia RAM para evitar la lentitud de los discos duros mecánicos viejos.
  * **Ananicy-cpp:** Sistema inteligente que gestiona los hilos del procesador, dándole máxima prioridad a la aplicación que estés usando y durmiendo los procesos en segundo plano.
* 🛠️ **Preparado para compilar (AUR):** Incluye `base-devel` y los *headers* del kernel por defecto. Esto es vital para hardware antiguo, ya que permite compilar drivers Wi-Fi de la comunidad o cualquier paquete del AUR sin dolores de cabeza.
* 🔌 **Instalador Offline Blindado:** Utiliza el instalador de CachyOS (Calamares) pre-configurado para instalar todo el sistema directamente desde el pendrive, sin depender de descargas por internet (`NetInstall` desactivado).

---

## 📥 Descarga e Instalación

1. Ve a la sección de **[Releases](../../releases)** en este repositorio.
2. Descarga la última versión de la ISO (`CachyOS-Legacy-vX.X-x86_64.iso`).
3. "Flashea" la ISO en un pendrive USB (recomendamos usar [Ventoy](https://www.ventoy.net/), [Rufus](https://rufus.ie/) o [BalenaEtcher](https://balena.io/etcher/)).
4. Arranca tu PC desde el USB.
5. Una vez en el escritorio XFCE, haz doble clic en el ícono **"Instalar CachyOS Legacy"** para iniciar Calamares.

---

## ⚙️ ¿Cómo está construido?

Este proyecto utiliza **GitHub Actions** para compilar la ISO automáticamente en la nube utilizando la herramienta oficial `mkarchiso`. 

Durante el flujo de trabajo (`build-iso.yml`):
1. Se descargan las firmas y repositorios oficiales de CachyOS.
2. Se eliminan los repositorios estrictos (`v3` y `v4`) dejando solo el genérico.
3. Se inyectan parches dinámicos (enlaces simbólicos) para evitar problemas de dependencias Rolling Release (`libyaml`, `boost`).
4. Se configuran los módulos de Calamares en modo `unpackfs` para asegurar una instalación limpia.

### Paquetes incluidos
La lista exacta de paquetes instalados se encuentra en el archivo `packages-legacy.txt`. Está estrictamente depurada para evitar "bloatware" de redes o herramientas de servidor innecesarias en un entorno de escritorio.

---

## 🤝 Créditos

Basado en el trabajo increíble del equipo de [CachyOS](https://cachyos.org/) y el ecosistema de Arch Linux.
