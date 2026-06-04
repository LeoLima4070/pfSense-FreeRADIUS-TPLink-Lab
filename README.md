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

---

## Ambiente de Testes

### Hardware

* TP-Link WR829N
* Adaptador USB Wi-Fi
* Notebook utilizado como plataforma de laboratório

### Software

* pfSense
* FreeRADIUS


## Evidências

As capturas de tela incluídas neste repositório demonstram:

* Configuração do FreeRADIUS no pfSense
* Cadastro de usuários
* Configuração WPA2-Enterprise no Access Point
* Integração do cliente RADIUS
* Conexão bem-sucedida à rede Wi-Fi

Também são disponibilizadas fotografias do ambiente físico utilizado durante os testes.

## Resultados

O ambiente foi configurado com sucesso, permitindo a autenticação centralizada de usuários em uma rede Wi-Fi através do protocolo WPA2-Enterprise.

O projeto demonstra a integração funcional entre pfSense, FreeRADIUS e um Access Point TP-Link, servindo como base para estudos de autenticação em redes sem fio.