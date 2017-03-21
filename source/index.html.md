---
title: API Reference

language_tabs:
  - http
  - shell
  - php

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - authentication
  - workflow
  - taxpayer
  - errors

search: true
---

# Introduction

Bienvenido al API de MonetaCore, plataforma desarrollada para la gestión de las obligaciones fiscales de los contribuyentes ante el SAT.

En MonetaCore, proporciona una biblioteca de funcionalidades expuestas al cliente que:

* Permite la creación de contribuyentes de tipo Persona Física, así como la gestión de los mismos.
* Permite obtener la lista de precios de cada uno de los servicios que se ofrecen.
* Permite realizar una declaración mensual, anual, regularización y complemento.
* Permite la creación de CFDIs. 
* Permite la creación de contadores, así como la gestión de los mismos.

MonetaCore está desarrollada bajo la arquitectura REST y se utilizan los verbos del protocolo HTTP (GET, POST, PUT y DELETE) para el consumo de los servicios, todos los servicios responden en formato JSON.

En la documentación expuesta a continuación se describen cada una de las funcioanalidades de la bibliteca.

# Cerberus

Capa de abstración responsable de la autorización de ejecución de servicios, así como el logeo de los autenticación de los clientes y usuarios en la plataforma. Todos los servicios expuestos requieren que en las cabeceras del protocolo HTTP anexar el token de acuerdo al tipo de servicio; a continuación se describe brevemente cada uno de ellos:  

Tipo de Token | HTTP Header | Descripción
--------- | --------- | -----------
Connection | x-token | Token asignado a un cliente con credenciales válidas que desea consumir servicios expuestos disponibles para todos, ejemplo Catálagos.
Session | x-token | Token asignado a un usuario con credenciales válidas, que le permitirán ejecutar servicios que por la delicadeza de la información es necesario conocer al resposable de la ejecución, ejemplo: actualización de la información de perfil.
Transaction | x-token | Token creado por un usuario con Session válida para la ejecución de servicios que requieren iniciar una transacción para el flujo de un proceso, por ejemplo pagar un servicio.


