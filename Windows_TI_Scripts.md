# Windows TI - Colección de Scripts Prácticos para Soporte (En Desarrollo)

## PowerShell Scripts

### Script 1: Revisión de Espacio en Disco
Get-PSDrive -PSProvider 'FileSystem' | Select-Object Name, @{Name="Free(GB)";Expression={[math]::round($_.Free/1GB,2)}}, @{Name="Used(GB)";Expression={[math]::round(($_.Used)/1GB,2)}}

### Script 2: Buscar archivos mayores a 500 MB y exportar a CSV
Get-ChildItem -Path "C:\" -Recurse -ErrorAction SilentlyContinue |
Where-Object { !$_.PSIsContainer -and $_.Length -gt 500MB } |
Select-Object FullName, @{Name="Size(GB)";Expression={[math]::round($_.Length/1GB,2)}} |
Export-Csv "C:\Temp\Archivos_Grandes.csv" -NoTypeInformation

### Script 3: Limpieza de Logs antiguos (> 30 días)
$logPath = "C:\Logs"
$dias = 30
Get-ChildItem -Path $logPath -Recurse | Where-Object { $_.LastWriteTime -lt (Get-Date).AddDays(-$dias) } | Remove-Item -Force

### Script 4: Verificar servicios críticos
$servicios = @("Spooler", "wuauserv", "BITS")
foreach ($svc in $servicios) {
    $estado = Get-Service -Name $svc
    if ($estado.Status -ne "Running") {
        Write-Output "$svc no está en ejecución"
    }
}

### Script 5: Reinstalar software con Chocolatey
$apps = @("googlechrome", "7zip", "notepadplusplus")
foreach ($app in $apps) {
    choco install $app -y --force
}

### Script 6: Información de usuario y dominio
$usuario = [System.Security.Principal.WindowsIdentity]::GetCurrent().Name
$dominio = (Get-WmiObject Win32_ComputerSystem).Domain
Write-Output "Usuario actual: $usuario"
Write-Output "Dominio: $dominio"

### Script 7: Apagar o reiniciar remotamente
Restart-Computer -ComputerName PC001 -Force
# Stop-Computer -ComputerName PC001 -Force

### Script 8: Exportar software instalado a CSV
Get-ItemProperty HKLM:\Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\* |
Select-Object DisplayName, DisplayVersion, Publisher, InstallDate |
Export-Csv "C:\inventario.csv" -NoTypeInformation

### Script 9: Respaldo de Documentos del Usuario
$fecha = Get-Date -Format yyyyMMdd
$origen = "C:\Users\$env:USERNAME\Documents"
$destino = "D:\Backups\$env:USERNAME\Docs_$fecha"
Robocopy $origen $destino /MIR /R:2 /W:2

### Script 10: Enviar alerta por correo
$body = "Se detectó bajo espacio en disco en PC001"
Send-MailMessage -From "soporte@empresa.com" -To "ti@empresa.com" \
-Subject "Alerta de Espacio Crítico" -Body $body \
-SmtpServer "smtp.empresa.com"


## Comandos CMD (Batch)

### Comando 1: Ver IP y Gateway
ipconfig /all

### Comando 2: Ver procesos activos
tasklist

### Comando 3: Apagar equipo en 60 segundos
shutdown -s -t 60

### Comando 4: Reiniciar equipo inmediatamente
shutdown -r -t 0

### Comando 5: Mostrar lista de servicios
sc query

### Comando 6: Ver carpetas compartidas
net share

### Comando 7: Ver usuarios del sistema
net user

### Comando 8: Conectarse a unidad de red
net use Z: \\servidor\carpeta /user:DOMINIO\usuario

### Comando 9: Mostrar eventos del sistema
wevtutil qe System /f:text /c:5

### Comando 10: Ver tabla ARP (direcciones MAC)
arp -a

### Comando 11: Trazar ruta hacia un host remoto
tracert www.google.com

### Comando 12: Verificar conectividad con ping
ping 8.8.8.8

### Comando 13: Ver puertos abiertos y conexiones activas
netstat -an

### Comando 14: Actualizar directivas de grupo
gpupdate /force

### Comando 15: Forzar cierre de sesión remota
logoff <ID>

### Comando 16: Activar hibernación
powercfg /hibernate on

### Comando 17: Ver configuración de energía
powercfg /query

### Comando 18: Diagnóstico de batería (laptops)
powercfg /batteryreport /output "C:\battery_report.html"

### Comando 19: Ver configuración de red
net config workstation

### Comando 20: Mostrar configuración DNS
nslookup www.google.com


## Comandos Git

### Verificar configuración global del usuario
git config --global user.name

### Establecer nombre y correo global
git config --global user.name "Tu Nombre"
git config --global user.email "correo@dominio.com"

### Clonar un repositorio
git clone https://github.com/usuario/repositorio.git

### Ver el estado del repositorio local
git status

### Ver historial de commits
git log

### Añadir todos los archivos al área de staging
git add .

### Hacer commit con mensaje
git commit -m "Mensaje descriptivo"

### Subir cambios al repositorio remoto
git push origin main

### Traer actualizaciones del repositorio remoto
git pull origin main

### Crear una nueva rama
git checkout -b nueva-rama

### Cambiar a una rama existente
git checkout nombre-rama

### Fusionar una rama en la actual
git merge nombre-rama

### Ver ramas disponibles
git branch

### Eliminar rama local
git branch -d nombre-rama

### Ver diferencias entre archivos modificados
git diff

### Revertir cambios locales no guardados
git restore archivo.txt

### Ignorar archivos (usar .gitignore)
# Crear archivo .gitignore en raíz del proyecto
# Ejemplo:
```bash
*.log
/temp/
secret.txt

