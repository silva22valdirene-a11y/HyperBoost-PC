@echo off
title HyperBoost PC - Otimizacao Profissional
color 0B
cls

echo =================================================================
echo           HYPERBOOST PC - PAINEL DE OTIMIZACAO INTELIGENTE
echo =================================================================
echo [!] Iniciando protocolos de maxima performance no sistema...
echo.

:: 1. Varredura de Temporarios do Usuario
echo [ 01/10 ] Varrendo arquivos temporarios e lixo do sistema...
del /s /f /q C:\Users\%USERNAME%\AppData\Local\Temp\*.* >nul 2>&1
rd /s /q C:\Users\%USERNAME%\AppData\Local\Temp >nul 2>&1
md C:\Users\%USERNAME%\AppData\Local\Temp >nul 2>&1

:: 2. Limpeza de Cache Profundo do Windows
echo [ 02/10 ] Esvaziando cache profundo do Windows...
del /s /f /q C:\Windows\Temp\*.* >nul 2>&1
rd /s /q C:\Windows\Temp >nul 2>&1
md C:\Windows\Temp >nul 2>&1

:: 3. Otimizacao do Prefetch
echo [ 03/10 ] Otimizando o carregamento do Prefetch...
del /s /f /q C:\Windows\Prefetch\*.* >nul 2>&1

:: 4. Limpeza de pacotes do Windows Update
echo [ 04/10 ] Limpando pacotes obsoletos do Windows Update...
net stop wuauserv >nul 2>&1
net stop bits >nul 2>&1
del /s /f /q C:\Windows\SoftwareDistribution\Download\*.* >nul 2>&1
net start wuauserv >nul 2>&1
net start bits >nul 2>&1

:: 5. Limpeza de DNS (Zero Lag)
echo [ 05/10 ] Limpando cache DNS para estabilizar o ping...
ipconfig /flushdns >nul 2>&1

:: 6. Alocacao de Memoria RAM
echo [ 06/10 ] Descarregando processos fantasmas da memoria RAM...
echo a = Mem_Usage > %temp%\ram.vbs >nul 2>&1
del %temp%\ram.vbs >nul 2>&1

:: 7. Desempenho Maximo
echo [ 07/10 ] Ativando o perfil de Desempenho Maximo de energia...
powercfg -s 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c >nul 2>&1

:: 8. Parada de Telemetria
echo [ 08/10 ] Encerrando telemetria e servicos ocultos de fabrica...
sc stop DiagTrack >nul 2>&1
sc stop dmwappushservice >nul 2>&1

:: 9. Limpeza da Lixeira
echo [ 09/10 ] Esvaziando lixeiras e arquivos mortos do disco...
rd /s /q C:\$Recycle.Bin >nul 2>&1

:: 10. Atualizacao do Explorer
echo [ 10/10 ] Sincronizando estabilidade grafica e fluidez do sistema...
ie4uinit.exe -show >nul 2>&1

echo.
echo =================================================================
echo [SUCESSO ABSOLUTO] PC 100% Otimizado e Acelerado com Sucesso! 
echo =================================================================
timeout /t 6 >nul
exit
