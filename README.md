Overview
SREGS is a compact 314-byte program designed for HP-42s, Swissmicro DM42 and Free42 calculators to provide a simple, 
menu-driven interface for browsing and manipulating indirect registers. 
It allows users to quickly view, modify, and transfer values between the X-register and indirect memory locations using intuitive key mappings.

Features
Register Selection via Keys 1–4 Quickly set the indirect register pointer (TEMPSRE) to R00, R05, R10, or R20.
Transfer Functions via Keys 5–6
Key 5: Store X into the selected register (X→RG)
Key 6: Recall value from the selected register into X (RG→X)
Scroll Register Index via Keys 7–8
Key 7: Increment TEMPSRE (up to 23)
Key 8: Decrement TEMPSRE (down to 0)
Clear & Exit via Key 9 Clears the menu and variable TEMPSRE, then exits the program.
Live Register View The current register index is shown using VIEW IND "TEMPSRE".

How It Works
The program uses a variable TEMPSRE to store the current indirect register index.
The main loop (LBL 00) displays a menu and waits for key input.
Each key press routes to a corresponding label (LBL 01 to LBL 09) to perform the desired action.
Keys 7 and 8 include bounds checking to prevent overflow/underflow of the register index.
Keys 5 and 6 use indirect addressing to store/recall values.

Initialization
On launch:
PROFF turns printing off(otherwise view prints every register change)
CLMENU clears any previous menu.
TEMPSRE temporary variable is initialized to 0.

Exit Behavior
Key 9 (LBL 09) clears the menu and deletes TEMPSRE, then halts execution.

Requirements
Compatible with HP42S and DM42 calculators.

No external libraries or dependencies.
