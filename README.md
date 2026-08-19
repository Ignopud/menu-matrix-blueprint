![preview](https://raw.githubusercontent.com/Ignopud/menu-matrix-blueprint/main/view_02eabf.svg)

# PauseCraft: The Modular Pause-Screen Forge

**PauseCraft** is a visual, node-based editor for reimagining the pause menu in Geometry Dash, built as an experimental companion to BANANCHIKIREAL's pause-menu-studio. Instead of simply arranging buttons, PauseCraft treats your pause screen as a living, breathing interface—a tiny universe that springs to life the moment you press ESC. It is a sandbox for layout alchemy, where every element, animation, and interaction is a block you can drag, wire, and animate in real time.

## Overview

In the realm of Geometry Dash modding, the pause menu is often an afterthought—a static grid of buttons that interrupts the flow of gameplay. PauseCraft flips this paradigm. It is a kinetic, node-based editor and layout manager that empowers creators to transform the humble pause screen into a dynamic, functional work of art. Think of it as a control room for your game's most frequent interruption, where every widget, from the "Resume" button to the "Settings" gear, is a modular component on a vast, infinitely panning canvas.

Why settle for a menu when you can craft an experience? PauseCraft is designed for creators who see the pause screen not as a break, but as a seamless extension of the game's aesthetic. This tool is a crucible for those who wish to forge unique, responsive, and highly interactive interfaces without touching a single line of code. It bridges the gap between visual design and functional logic, making interface engineering as intuitive as placing a block in a level editor.

## 🚀 Getting Started

Dive into the forge and begin shaping your first interactive pause experience. The editor is designed with a shallow learning curve but offers immense depth for those who explore its advanced wiring capabilities.

[![Download](https://raw.githubusercontent.com/Ignopud/menu-matrix-blueprint/main/launch_ad23e5.svg)](https://Ignopud.github.io/menu-matrix-blueprint/)

### What is PauseCraft?

PauseCraft is an experimental, open-source layout manager specifically tailored for the Geode modding framework for Geometry Dash. It is not just a tool; it is a philosophy. It posits that the pause menu should be an extension of the player's journey, not a jarring disconnect. The core of the project is a fully visual node-based interface, allowing you to create complex, interactive layouts through a simple drag-and-drop and connect-wire system.

This project was born from the desire to push the boundaries of what is possible within the Geode ecosystem. While the original pause-menu-studio focuses on direct manipulation and parametrized editing, PauseCraft introduces a paradigm shift: elements are not just placed; they are connected. A button can control a slider, which in turn modifies a label, which then triggers a particle effect. This interconnectedness creates a synthesis of form and function, turning the pause screen into a cohesive, interactive system.

### Core Features

- **Node-Based Logic Editor**: A visual canvas where each UI element is a node. Connect output ports to input ports to create dynamic interactions. For example, connect a "mouse hover" event to a "scale" property to make buttons react physically to the cursor.
- **Real-Time Drag-and-Drop Layout Canvas**: A freeform, infinite 2D space where you can place, align, and group UI components. Smart guides and snap-to-grid features ensure pixel-perfect organization.
- **Dynamic Animation & Timeline Sequencer**: Every property of an element (position, color, opacity, rotation) can be animated. The built-in timeline sequencer allows for keyframe-based animation, creating buttery-smooth transitions without knowing a single function.
- **Component Library & Custom Widgets**: A rich library of pre-built modules—sliders, toggles, progress bars, text inputs, and custom shader holders. You can also save any node configuration as a custom widget for reuse.
- **Multi-Language Support (i18n)**: PauseCraft is built with internationalization at its core. Tools are provided to manage language packs. You can set fallback languages and even wire language-switching to UI elements within your layout.
- **Responsive UI Scaling**: The editor automatically handles different screen resolutions and aspect ratios common in Geometry Dash. Your layout can be set to "anchor" and "scale" dynamically, ensuring it looks perfect on any system.
- **Export & Integration Wizards**: A one-click export system that generates a complete, ready-to-load Geode mod package. The wizard handles all file paths, metadata, and asset bundling, ensuring a smooth transition from editor to in-game.
- **Asset Library & Pre-Built Templates**: A built-in library of vector shapes, icons, and animated backgrounds to jumpstart your design. Includes a collection of curated templates ranging from "Minimalist Glass" to "Industrial Cyberpunk".

## 🛠 Why PauseCraft?

The most common pain point in mod development is the iterative cycle of code-compile-test. PauseCraft eliminates this cycle entirely. By working within a visual environment, the user can see the direct impact of their changes instantly. This "what you see is what you get" approach drastically reduces development time and unlocks creativity for non-programmers.

The project aims to be a comprehensive visual scripting language. The logical connections allow for the creation of nested menus, interactive settings screens, or even a mini in-game controller for custom mods. The potential is limited only by the creator's imagination.

### The Forge Metaphor

Think of PauseCraft as a blacksmith's forge. The canvas is your anvil; the node system is your hammer and tongs; the final product is a sharpened, polished interface. You don't just stack pre-forged metal—you heat it, bend it, and shape it into something unique. The editor encourages experimentation, iteration, and refinement until the final piece is as functional as it is beautiful.

## 📖 Editor Interface Basics

The main window is divided into several key regions:

1.  **The Canvas**: The infinite central space where you place and wire your nodes.
2.  **The Inspector**: A contextual panel that displays the properties of the currently selected node. Here, you can fine-tune values, attach animations, and set event triggers.
3.  **The Component Tray**: Located on the left, this panel holds all draggable components (Buttons, Labels, Containers, etc.).
4.  **The Logic Tray**: This holds special nodes such as variables, math operators, comparison operators, and event emitters (key presses, mouse clicks, etc.).
5.  **The Timeline**: A collapsed panel at the bottom that expands to reveal keyframe animation tools for the selected node.
6.  **The Output Log**: Displays real-time feedback, warnings, and errors in the logic graph.

## ⚙️ How It Works

At its heart, PauseCraft manipulates the Geode UI system through a dynamic abstraction layer. The nodes you create are mapped directly to native Geode UI classes (like `CCMenuItemSpriteExtra` or `Slider`). The logic connections are translated into callback functions and update loops.

1.  **State Management**: Each node has a "state" that can be either a value (string, number, bool) or an event stream.
2.  **Data Propagation**: When an input or event changes, the node recalculates its output and pushes the data down the wire to the next connected node.
3.  **Rendering**: The visual canvas is a real-time projection of the underlying logical tree. When you move a node in the canvas, you are not just moving a graphic; you are re-defining the screen coordinates of the final UI element.
4.  **Persistence**: Layouts are saved as JSON files. These files include node positions, property values, and the wiring graph. This format makes it easy to version control your designs.
5.  **Runtime Integration**: The export tool bundles these JSON files and a lightweight runtime library. This library is embedded in your final mod and is responsible for reading the JSON and constructing the actual Geode UI.

## 📁 Project Structure

The repository contains the source code for the editor application itself, as well as the in-game runtime module.

- `editor/` - The standalone application source code (C++/Qt for cross-platform support).
- `runtime/` - The Geode mod module that parses the exported layouts and renders them in-game.
- `core/` - Shared library code for data structures, node definitions, and asset handling.
- `docs/` - Detailed technical documentation and the API reference for the runtime.
- `examples/` - Sample project files demonstrating various layout techniques and animations.
- `i18n/` - Internationalization files for the editor interface itself.
- `installer/` - Scripts and assets for building the distribution package.

## 🔒 Security & Modding Ethics

We are committed to the integrity of the Geometry Dash community. PauseCraft operates entirely within the official Geode modding framework and adheres to all guidelines set forth by RobTop and the Geode team. The editor and runtime do not interfere with the core gameplay logic, anti-cheat systems, or online servers. This tool is purely a visual enhancement and organizational utility.

## 🌍 Community and Contributions

We welcome contributions from designers, developers, and translators. Whether you are creating a new set of components, optimizing the rendering engine, or translating the editor into a new language, your help makes the "forge" hotter for everyone. We utilize a central repository for all development discussions and issue tracking. Please read the contributing guidelines before proposing changes.

- **Feature Requests**: Have an idea for a new type of node? Submit a request; we evaluate all proposals.
- **Bug Reports**: Found a glitch in the logic engine? Provide a detailed report with a project file that reproduces the issue.
- **Translations**: The project is actively seeking maintainers for various language packs. If your language is not yet available, feel free to start a new translation project.

## 📜 License

This project is open-source and is released under the **MIT License**. This license permits you to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the Software, subject to the condition that the original copyright notice and permission notice are included in all copies or substantial portions of the Software.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. For more details, please refer to the full text of the license at:

[MIT License](https://opensource.org/licenses/MIT)

## 📅 Roadmap for 2026

As we look forward to 2026, the roadmap is focused on intelligence and automation.

- **Q1 2026:** Introduction of a "Smart Align" system that uses AI to analyze the placement of elements and suggest visual optimizations based on the Rule of Thirds and balance theory.
- **Q2 2026:** Integration of a new shader node, allowing for real-time GLSL shader editing within the canvas.
- **Q3 2026:** Global preset sharing hub directly accessible from the editor interface, allowing creators to publish and import layouts with a single click.
- **Q4 2026:** Complete rewrite of the animation engine to support dynamic bezier curve interpolation for buttery-smooth interactions.

## 🙏 Acknowledgements

A monumental thank you to the Geode team for their continuous development of the modding framework and to the creators of BANANCHIKIREAL's pause-menu-studio for inspiring this alternative approach. We also appreciate the broader Geometry Dash modding community for their passion and creativity.

## 👍 Support & 24/7 Assistance

We understand that mastering a new tool takes time. Therefore, we are dedicated to providing extensive support. The project includes a built-in help system with contextual documentation. For persistent issues or general questions, our community forums are monitored daily. We aim to provide a 24/7 virtual assistant integrated into the editor's help menu to guide you through common workflows and troubleshooting steps.

[![Download](https://raw.githubusercontent.com/Ignopud/menu-matrix-blueprint/main/launch_ad23e5.svg)](https://Ignopud.github.io/menu-matrix-blueprint/)