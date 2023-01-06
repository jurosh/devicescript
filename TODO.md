# TODO

### treat roles as "normal" objects
* actually call `Command.__func__`
* `Register.onChange` threshold handling
* `Event.subscribe`
* `Event.wait`
* `Condition` handling
* register delay computation
* Role.sendCommand
* `[a,b,c] = reg.read()`

## Random stuff
* change `ALLOC_*` opcodes to expressions
* `Object.keys(spec_object)` ?
* validate UTF8 on input
* fix charAt() etc to decode UTF8
* add `JSON.parse/stringify()`

## Big ticket
* buffer overflows when printing a lot
* drop type-directed compilation
* try/catch - devs_runtime_failure() vs devs_raise()

* role.packet -> (roleidx, spec-offset)
* led.active.__proto__.foo = ... ? nope. frozen.

## General usability

* drop seconds, use milliseconds everywhere
* multi-program LATER
* hash-consing of strings? (esp. for JSON parsing) LATER
* tree strings?

* hang properties off roles - `high`, `lastHigh` for bar graph eg
* `role.control` -> control service of device that has this role ?
* role for control service of the brain (to set status light, reset, etc)
* add opcode to cache current packet (in onChanged())
* shift buffer opcode?
* somehow deal with events with legit args (button and barcode reader currently) - doesn't work so well in handler-pending model
* add `role.waitConnected()` or something?
* add `bg(() => { ... })`, also `bg1()` ?
* do fiber round-robin for yields?
* some testing framework? (depends on services?)

## Implementing services in DeviceScript

* this generally doesn't work with handler-pending model
* opcode to send current packet
* opcode to set the command
* opcode to set service number
* some way of building announce packets
* handler when a packet is received
* support 1 or more devices per VM instance?
* add `try_again` report in addition to `command_not_implemented` ?

## Cloud

* specific uploads: `hum.autoUpload(5, 1) // 5s, 1%`
* auto-upload of everything

## Debugger interface

* fiber list, locals, globals
* setting breakpoints - breakpoint instruction? (based on source code location)
* more "debug" info in compiled program - role names, etc for error messages?
