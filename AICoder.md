Context & Skill Level

FYI: I am a Flutter developer with limited professional experience, but I have a solid understanding of programming fundamentals, real-world application logic, and clear data flow.

Your Role

Act as a seasoned programmer and technical AI assistant. You will provide expert-level guidance and write production-quality code in Dart/Flutter (desktop) and Python (backend). Your focus should be on AI-integrated desktop utilities, global input handling, real-time streaming, and system-level UX.
You should follow best practices, write clean and maintainable code, optimize for performance, and document everything clearly so it is easy to extend later.

Project Description

I am building a desktop Flutter application that:

Captures screenshots directly from the clipboard (e.g., via Print Screen)

Sends the screenshot discreetly to a Python backend (no browser interaction)

Prompts an AI LLM (Gemini API) using either fast text input or voice input

Displays AI responses in a floating overlay GUI that stays on top of all other applications

Streams responses in real time using SSE

Current Progress

Flutter UI connected to a Python backend using the Gemini API

Clipboard screenshot capture implemented using super_clipboard

Backend SSE streaming already working

Planning a separate Dart file for the overlay window (rounded rectangle, semi-transparent blue, always-on-top)

🔴 Current Objective: Global Hotkey System (Flutter Desktop)

Your task is to design and implement the global hotkey system using:

hotkey_manager: ^0.2.3


The solution must work at the system level, meaning the hotkeys function even when the app is not focused.

Goals
1. Screenshot Upload Hotkey

Implement a global hotkey that:

Key combo: Ctrl + Alt + Shift + U

Immediately:

Reads the current screenshot from the clipboard

Sends it to the backend AI LLM pipeline

Does not interrupt the user’s active application

Should be debounced and safe against repeated triggers

2. Prompt Mode Toggle Hotkey

Implement a global hotkey that toggles a Prompt Mode:

Key combo: Ctrl + Alt + Shift + P

When Prompt Mode is ON:

The overlay becomes visible and focused

Keyboard input is exclusively captured by a text input field

User can type a prompt immediately

No other app should receive keyboard input

When Prompt Mode is OFF:

Overlay input is released

Keyboard control returns to the OS and active apps

Prompt mode can only be exited by pressing the same hotkey again

This logic must be:

Explicit

State-driven

Safe from focus loss bugs

3. Overlay Scrolling via Hotkeys

Implement global scrolling controls for the overlay content:

Scroll Up
Ctrl + Alt + Shift + Up Arrow

Scroll Down
Ctrl + Alt + Shift + Down Arrow

These hotkeys should:

Scroll the SSE response content inside the overlay

Work even when the overlay is not focused

Respect scroll bounds and avoid jitter

Implementation Expectations

Use hotkey_manager correctly with proper lifecycle handling

Clearly separate:

Hotkey registration

State management

UI overlay logic

Provide:

Dart code examples

Explanation of focus management and keyboard capture

Best practices for desktop Flutter hotkeys (Windows/macOS/Linux where applicable)

Ensure the solution integrates cleanly with:

The existing clipboard flow

The SSE streaming UI

The overlay window system
