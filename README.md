# modbus-rtu-slave
Provides basic nodes for simulating a modbus RTU slave.
Provides the following nodes:
- Modbus-RTU-Slave: Slave itself; listens on the configured port for RTU requests and responds with requested values; values can be updated either over port using write commands, or directly using the node's input. Can contain upto 50000 values in each register.
- Modbus-RTU-Writer: A helper node for making writing common values directly into the Slave's input; can write addresses both in the local range [0:9999] and the global range [1:50000].
 
e.g, when writing the address 30001, it will always be written into the Input registers, since addresses [30001:40000] are conventionally the Input registers. When using the 'convertToLocal' option when writing, the address 30001 would automatically be converted to the address 0 (of the Input registers). If NOT using the 'convertToLocal' option, the address 30001 would stay as 30001. Since all buffers allow upto 50000 values, this would also work and not overflow into another buffer. (This unconventional approach is supported due to a requirement of a project.)
--------------------------------------------------------------------------------------

Simulacion del protocolo modbusRTU en node-red utilizando dos conversores usb/485. 
<img width="915" height="323" alt="Captura de pantalla de 2025-09-07 11-56-30" src="https://github.com/user-attachments/assets/a3952937-884b-4018-96ff-ef3e096d8fe4" />
![usb-485](https://github.com/user-attachments/assets/4f65d119-697c-415b-a048-e0d5cf2acc6a)
Descargar flow en -> examples/flows2.json

