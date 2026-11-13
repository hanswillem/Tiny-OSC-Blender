# Tiny OSC Blender

A small Blender add-on for receiving OSC messages and mapping them to Blender properties. Designed with TouchDesigner in mind, but probably, maybe, compatible with Pure Data, Max/MSP and other OSC-capable tools.

## Installation & Setup
1. Download **tiny_osc.py**, and install through Blender's preferences.
2. Find it in the **N-Panel** of the viewport.
3. Under **Connection:**, set the UDP port (default **10000**) and press **Listen**.

Tiny OSC listens on **localhost (127.0.0.1)** only. Run your OSC sender on the same computer and send to this address and port.

The add-on applies incoming OSC values continuously at ~60 Hz. Received values are shown at the bottom in real time for quick feedback.

## Making Mappings
- Under **Mappings:**, click the **+** button to add a new mapping. New mappings appear below it.
- Enter the **OSC Address**. In TouchDesigner this is the channel name being sent over OSC.
- Click the eyedropper next to **Blender Full Data Path**, then click a numeric property in Blender to capture its path. Pick an individual component for vector properties, such as Location X. Press **Esc** or right-click to cancel.
- Alternatively, right-click a property, choose **Copy Full Data Path**, and paste it into the field.

You can target most Blender properties. Just try it.

## Baking Keyframes
- With **Listen** enabled and at least one mapping configured, place the playhead anywhere in the timeline and click **Bake Keyframes** under **Record:**, below the mappings. Blender will start playback and insert keys as OSC values arrive.

The resulting animation curves can look a bit wonky, but wonky is good.
