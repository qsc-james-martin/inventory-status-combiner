# Inventory Status Combiner

## See the worst status across a design in one place.

When a design contains many components, checking their inventory status one at
a time makes it easy to miss a fault. Inventory Status Combiner polls every
design inventory item and reports the highest status code, along with a list
of non-OK items, without requiring input wiring.

## What it reports

The combined status follows Q-SYS Status Combiner priority: the highest
numeric status code wins. The panel also has OK, Compromised, and Fault
indicators. This plugin is not itself a managed inventory item.

## Additional inputs

Set **Additional Inputs** in the plugin properties to add status input pins
(0–64). These are combined with the design inventory statuses and can be
managed like the native Status Combiner:

- **Disable** excludes an input.
- **Suppress** temporarily excludes it until its status changes.
- **Latch** holds its last non-OK status until **Reset**.
- **Label** gives the input a name in the combined status message; blank labels
  default to `Input N`.

The inventory and wired inputs are checked once per second. Status changes,
including healthy states and faults, always print to the Q-SYS log. Unchanged
status is not repeatedly logged; there is no Debug Print property.
