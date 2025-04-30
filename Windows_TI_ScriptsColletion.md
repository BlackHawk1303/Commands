## Estructura del Repositorio

El repositorio está dividido en tres categorías principales:

- **PowerShell Scripts**: Scripts para tareas administrativas avanzadas en PowerShell.
- **CMD Scripts**: Comandos en CMD (Batch) para tareas comunes de administración.
- **Git Commands**: Comandos útiles para trabajar con Git.

### Carpetas

- **PowerShell**: Scripts para gestionar espacio en disco, servicios, backups, y más.
- **CMD**: Comandos básicos para operaciones del sistema.
- **Git**: Comandos relacionados con Git, para manejar repositorios de código.

## Scripts Disponibles

### PowerShell Scripts
1. **Revisión de Espacio en Disco**  
   Verifica el espacio libre y utilizado en las unidades de almacenamiento locales del sistema.  
   [Script PowerShell](PowerShell/Script1-Revision-Espacio-Disco.ps1)

2. **Buscar Archivos Mayores a 500 MB y Exportar a CSV**  
   Encuentra archivos mayores a 500 MB y exporta la lista a un archivo CSV.  
   [Script PowerShell](PowerShell/Script2-Buscar-Archivos-Mayores.ps1)

3. **Limpieza de Logs Antiguos**  
   Elimina logs de más de 30 días de antigüedad.  
   [Script PowerShell](PowerShell/Script3-Limpieza-Logs.ps1)

4. **Verificar Servicios Críticos**  
   Verifica el estado de servicios críticos como el Spooler, Windows Update y BITS.  
   [Script PowerShell](PowerShell/Script4-Verificar-Servicios.ps1)

5. **Reinstalar Software con Chocolatey**  
   Reinstala aplicaciones usando Chocolatey.  
   [Script PowerShell](PowerShell/Script5-Reinstalar-Software.ps1)

6. **Información de Usuario y Dominio**  
   Muestra información sobre el usuario actual y el dominio al que pertenece.  
   [Script PowerShell](PowerShell/Script6-Informacion-Usuario-Dominio.ps1)

7. **Apagar o Reiniciar Remotamente**  
   Permite apagar o reiniciar una máquina de manera remota.  
   [Script PowerShell](PowerShell/Script7-Apagar-Reiniciar-Remoto.ps1)

8. **Exportar Software Instalado a CSV**  
   Exporta el software instalado en el sistema a un archivo CSV.  
   [Script PowerShell](PowerShell/Script8-Exportar-Software-Instalado.ps1)

9. **Respaldo de Documentos del Usuario**  
   Realiza un respaldo completo de los documentos del usuario a una ubicación específica.  
   [Script PowerShell](PowerShell/Script9-Respaldo-Documentos.ps1)

10. **Enviar Alerta por Correo**  
    Envía una alerta por correo cuando se detecta un evento específico.  
    [Script PowerShell](PowerShell/Script10-Enviar-Alerta-Correo.ps1)

### CMD Scripts
1. **Ver IP y Gateway**  
   Muestra la información de IP y Gateway de la máquina.  
   [Comando CMD](CMD/Comando1-Ver-IP.ps1)

2. **Ver Procesos Activos**  
   Muestra los procesos activos en el sistema.  
   [Comando CMD](CMD/Comando2-Ver-Servicios.ps1)

3. **Apagar Equipo en 60 Segundos**  
   Apaga el equipo en 60 segundos.  
   [Comando CMD](CMD/Comando3-Apagar-Equipo.ps1)

4. **Reiniciar Equipo Inmediatamente**  
   Reinicia el equipo sin demora.  
   [Comando CMD](CMD/Comando4-Reiniciar-Equipo.ps1)

5. **Mostrar Lista de Servicios**  
   Muestra la lista de servicios activos.  
   [Comando CMD](CMD/Comando5-Mostrar-Eventos.ps1)

### Git Commands
1. **Verificar Configuración Global del Usuario**  
   Verifica la configuración global del usuario en Git.  
   [Comando Git](Git/Comando1-Verificar-Config-Usuario.ps1)

2. **Clonar Repositorio**  
   Clona un repositorio de Git.  
   [Comando Git](Git/Comando2-Clonar-Repositorio.ps1)

3. **Ver Estado del Repositorio Local**  
   Muestra el estado actual de los archivos en el repositorio local.  
   [Comando Git](Git/Comando3-Ver-Estado.ps1)

## Instrucciones para Ejecutar los Scripts

1. **PowerShell Scripts**  
   Para ejecutar los scripts de PowerShell, abre una ventana de PowerShell como administrador y navega al directorio donde se encuentra el script. Ejecuta el script con el siguiente comando:

   ```powershell
   .\NombreDelScript.ps1
