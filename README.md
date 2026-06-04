# Implementação de Autenticação Wi-Fi WPA2-Enterprise com pfSense e FreeRADIUS

## Visão Geral

Este projeto demonstra a implementação de autenticação centralizada para uma rede Wi-Fi utilizando WPA2-Enterprise (802.1X), com o FreeRADIUS integrado ao pfSense e um Access Point TP-Link WR829N operando em modo AP.

O objetivo é validar o processo de autenticação de usuários por meio de credenciais individuais, utilizando uma infraestrutura simples composta por hardware doméstico e software open source.

---

## Objetivos

* Implementar autenticação Wi-Fi baseada em usuário e senha.
* Integrar o FreeRADIUS ao pfSense.
* Configurar um Access Point para utilizar autenticação WPA2-Enterprise.
* Validar o fluxo completo de autenticação em ambiente de laboratório.

---

## Topologia

A topologia do laboratório é composta pelo pfSense atuando como roteador principal da rede, responsável pelo gerenciamento da LAN, fornecimento de DHCP e integração com um servidor RADIUS previamente configurado.

A rede LAN 192.168.1.0/24 é utilizada como segmento principal, onde o ponto de acesso TP-Link, configurado em modo Access Point e com endereço IP estático 192.168.1.4, atua como cliente RADIUS.

O TP-Link é responsável pela distribuição do sinal Wi-Fi aos dispositivos sem fio, enquanto a autenticação dos usuários é centralizada no pfSense por meio do serviço RADIUS, garantindo controle de acesso à rede.

Por fim, a interface WAN do pfSense fornece conectividade com a internet.

![Topologia da rede](Topologia/Topologia.png)

## Tecnologias Utilizadas

* pfSense
* FreeRADIUS
* WPA/WPA2-Enterprise (802.1X)
* TP-Link WR829N (Modo Access Point)

---

## Fluxo de Autenticação

1. O cliente tenta conectar-se à rede Wi-Fi.
2. O Access Point encaminha a solicitação de autenticação.
3. O FreeRADIUS recebe as credenciais.
4. O servidor valida usuário e senha.
5. O acesso é concedido ou negado.
6. Se concedido o cliente recebe um IP distribuído pelo pfSense via DHCP

---

## Configurações



### Hardware

* TP-Link WR829N
* Adaptador USB Wi-Fi
* Notebook utilizado como plataforma de laboratório


O hardware físico utilizado neste projeto consiste em um notebook com uma interface de rede Ethernet (RJ-45) integrada, além de uma placa de rede USB Ethernet adicional.

No VirtualBox, a máquina virtual do pfSense foi configurada com duas interfaces de rede em modo bridge. A primeira interface foi associada à placa de rede integrada do notebook, sendo configurada como WAN, responsável pelo acesso à internet.

O modo Bridge foi utilizado para que o pfSense operasse como um dispositivo de rede real, integrado diretamente à infraestrutura física, permitindo comunicação direta com o ponto de acesso TP-Link e demais dispositivos da rede, simulando um ambiente de produção.

A segunda interface foi associada à placa de rede USB Ethernet, sendo configurada como LAN, onde foi conectado o ponto de acesso TP-Link.

![Configuração das placas de rede no virtualbox](prints/VirtualBox/Config_rede_pfSense_virtualbox.png)

![tplink wr849n utilizado como AP](hardware/Roteador_TPlink-wr829n.jpeg)

![Placa de rede usb conectada ao tplink](hardware/Placa_de_rede_usb.jpeg)


### Software

* pfSense
* FreeRADIUS

## Testes




## Resultados

O ambiente foi configurado com sucesso, permitindo a autenticação centralizada de usuários em uma rede Wi-Fi através do protocolo WPA2-Enterprise.

O projeto demonstra a integração funcional entre pfSense, FreeRADIUS e um Access Point TP-Link, servindo como base para estudos de autenticação em redes sem fio.