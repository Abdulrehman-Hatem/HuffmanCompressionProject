# Huffman Compression Tool

This is a custom file compression and decompression utility built around the Huffman coding algorithm. 

I designed this project as a two-part system to keep the core algorithm highly performant while still being easy to use. The actual compression math runs through a C++ command-line tool, which is managed by a C# WinForms graphical interface.

### The Architecture

* **The Backend (C++)**: A standalone CLI tool (`FileCompression`) that handles all the low-level binary file processing. It handles building the Huffman tree, encoding the code tables directly into the file headers, and executing the bitwise compression (`-c`) and decompression (`-d`). 
* **The Frontend (C# .NET)**: A WinForms GUI that acts as a wrapper around the C++ executable. It handles process management in the background so you don't have to manually type out terminal commands.

### Features
* **Lossless Binary Handling**: Compresses and restores files perfectly using standard Huffman trees, with self-contained headers for the code tables.
* **Drag-and-Drop UI**: You can drag files straight into the GUI to queue them up.
* **Configurable Buffers**: Both the backend and frontend support adjustable buffer sizes, letting you tweak memory usage depending on what kind of files you are processing.
* **Standalone CLI Option**: If you prefer the terminal, you can bypass the GUI entirely and just run the C++ executable with the `-c` (compress) or `-d` (decompress) flags.

### Setup & Usage

1. Clone the repository and open the project in Visual Studio.
2. Build the C++ backend project first. The C# frontend needs this executable to be compiled so it can run the background processes.
3. Set the C# WinForms project as your startup project and run it.
4. Drag a file into the window, configure your buffer size if needed, and hit compress!
