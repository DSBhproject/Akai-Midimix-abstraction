# Akai-Midimix-abstraction
GOP abstraction for the Akai Midimix controller for plug and play use on Pure Data.

![Akai MIDImix GUI](gui.jpg)


🎚️ Akai MIDImix Abstraction for Pure Data
[akai.midimx] is a plug-and-play abstraction designed for the Akai MIDImix MIDI controller in Pure Data, with full compatibility for PlugData. Featuring a clean GOP layout, it integrates seamlessly into any patch for intuitive mixer-style control.

This abstraction builds on the previous [korg.nanokontrol2] design, adapted for Akai MIDImix — a controller without transport buttons but packed with faders, knobs, and mute switches.

⚙️ Features
🧩 Single-argument instantiation Just use the MIDI port number assigned in PD’s MIDI Settings.

🎛️ GOP-ready interface Embed in any parent patch with visual feedback and ease of control.

🌀 Plug-and-play workflow Instant connectivity with no manual mapping required.

💾 Savestate-friendly structure Works smoothly with patch saving across multiple instances.

🎧 Pure Data & PlugData compatible Flexible across environments and platforms.

🧰 Usage
To use the abstraction, place it in your patch like this:

puredata
[akai.midimx 1]
Where 1 is the MIDI port number corresponding to your Akai MIDImix in MIDI Settings.

📁 Included Files
akai.midimix.pd → main abstraction

akai.midimix-help.pd → help patch with preview layout

README.md → documentation file

Akai Editor template patch (recommended)

🔄 Interaction with Parent Patch
The [akai.midimx] abstraction is designed to be controlled and monitored from its parent patch, allowing full integration in larger modular setups.

📤 Sending Data to Parent Patch
The abstraction outputs values through its send outlet, which can be filtered using a [route <param_number>] object to retrieve the specific parameter value.

Example:

puredata
[route 3]
|
[param_value]
🔎 This lets you track control changes from the MIDImix in your main patch logic.

📥 Receiving External Control
You can also send control data into the abstraction using its receive inlet.

Use messages like:

[param_set <param_number> <param_value>(
To remotely change a parameter value (e.g., simulate fader movement or automation).

🧭 Parameter Labeling
You can assign names to parameters from the parent patch using:

[param_label <param_number> <param_name>( -> receive inlet
📝 This is useful for dynamic UI elements or identification in performance contexts.

📝 Notes
🔢 It has only one creation argument: the MIDI port number, which must match the number selected in PD's MIDI Settings.

📦 Else library is necessary for certain functions.

🧿 Multiple instances of [akai.midimix] are possible, but the help patch should remain closed to avoid conflicts.

🎛️ Use the abstraction in conjunction with the provided Akai Editor patch for full functionality.

✅ It is recommended to set the controller in CC Generic Mode — press CYCLE + SET MARKET while connecting the device to activate it.

👤 Credits
Developed by Diego @ DSB AUDIO
