- 👋 Hi, I’m @JULIO12232212212W322
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
JULIO12232212212W322/JULIO12232212212W322 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
class Cliente:
    def __init__(self, nombre, direccion):
        self.nombre = nombre
        self.direccion = direccion
        self.ropa_lavada = []

    def agregar_ropa_lavada(self, ropa):
        self.ropa_lavada.append(ropa)

    def generar_factura(self):
        total = 0
        print("Factura para:", self.nombre)
        print("Dirección:", self.direccion)
        print("Ropa lavada:")
        for ropa in self.ropa_lavada:
            print("- ", ropa["descripcion"], ": $", ropa["precio"])
            total += ropa["precio"]
        print("Total a pagar: $", total)


class Lavanderia:
    def __init__(self):
        self.clientes = []

    def agregar_cliente(self, cliente):
        self.clientes.append(cliente)

    def procesar_facturacion(self):
        for cliente in self.clientes:
            cliente.generar_factura()


# Ejemplo de uso
lavanderia = Lavanderia()

# Crear clientes
cliente1 = Cliente("Juan Perez", "Calle 123, Ciudad")
cliente2 = Cliente("María García", "Avenida 456, Pueblo")

# Agregar ropa lavada a los clientes
cliente1.agregar_ropa_lavada({"descripcion": "Camisa", "precio": 5.0})
cliente1.agregar_ropa_lavada({"descripcion": "Pantalón", "precio": 7.0})

cliente2.agregar_ropa_lavada({"descripcion": "Vestido", "precio": 10.0})
cliente2.agregar_ropa_lavada({"descripcion": "Camiseta", "precio": 3.0})

# Agregar clientes a la lavandería
lavanderia.agregar_cliente(cliente1)
lavanderia.agregar_cliente(cliente2)

# Procesar facturación
lavanderia.procesar_facturacion()
