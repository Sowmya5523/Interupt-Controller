 What is an Interrupt Controller?
An Interrupt Controller is a hardware block that handles interrupt signals from multiple devices or sources and determines the order in which the processor services them. It simplifies managing interrupts in systems with multiple peripherals.

Key Features:

Interrupt Prioritization: Determines which interrupt has the highest priority.
Masking: Allows enabling/disabling specific interrupts.
Interrupt Vectoring: Provides the appropriate service routine address for each interrupt.
Edge/Level Triggering: Supports different types of interrupt signals.
 Design of an Interrupt Controller
Components of the Design:
Interrupt Request (IRQ) Lines: Input lines where interrupt signals arrive.
Priority Resolver: Logic to determine which interrupt to service first.
Mask Register: Stores enable/disable status of interrupt lines.
Interrupt Vector Register: Provides the interrupt vector for the selected interrupt.
Interrupt Acknowledge: Signal to indicate that the interrupt is being serviced.

. Verification of the Interrupt Controller
Verification Overview:
The goal is to ensure that the Interrupt Controller behaves as expected under all scenarios:

Handles multiple IRQs with correct priority.
Acknowledges interrupts correctly.
Honors the masking of interrupts.

Simulation Results
Expected Outputs:
Test 1: The controller should acknowledge IRQ0 and set irq_vector = 2'b00.
Test 2: The controller should prioritize IRQ3 (irq_vector = 2'b11) when IRQ3 and IRQ1 are active.
Test 3: The controller should ignore IRQ3 when it is masked and prioritize IRQ2 (irq_vector = 2'b10).
Tools for Simulation:
Use tool ModelSim

Key Verification Metrics
Latency: Time between IRQ assertion and acknowledgment.
Priority Handling: Correctly prioritizing multiple simultaneous IRQs.
Masking Functionality: Ensuring masked interrupts are ignored.
Edge/Level Sensitivity: Correct detection of edge-triggered or level-triggered interrupts (if implemented).
