+++
tags = ['aws-fundamentals']
+++

# Fault Tolerance

This is what most people think [[high-availability]] is.

It is the property that enables a system to **continue operating properly** in
the event of the **failure of some** (1+ faults within) of its **components**.

There is a lot more care to the disruption that the user could face when
bringing a service back from a failing state. With [[high-availability]] you can
just swap the service with a stand by one, but state can be lost. With fault
tolerance there needs to be no loss of state from that faulty service swap. A
way to do this is by having multiple connections to various services so in case
there any issues with any service.

Fault tolerance is usually more expensive than [[high-availability]] since it
builds on top of the same fundamentals but tolerating the failure requires more
infra and redundant working components.
