---
title: API Reference

language_tabs:
  - shell: cURL

toc_footers:
  - <a href='http://kea.mx'>Documentation Powered by KEA</a>

includes:
  - endpoint
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

MonetaCore está desarrollada bajo la arquitectura REST y utiliza los verbos del protocolo HTTP (GET, POST, PUT y DELETE) para el consumo de los servicios, todos los servicios responden en formato JSON.

En la documentación expuesta a continuación se describen cada una de las funcionalidades de la biblioteca.

## Access Control

Capa de abstracción responsable de la autorización de ejecución de servicios, así como la autenticación de los clientes y usuarios en la plataforma. 

En MonetaCore REST API existen tres clasificaciones de servicios:

* **ConnectionService**: Aquellos servicios que requieren un token de tipo Connection, donde sus caracteristica principal es exponer información publica; por ejemplo Catálogos.

Todos los servicios expuestos requieren que en las cabeceras del protocolo HTTP se anexe el `x-token`; a continuación se describe brevemente cada uno de ellos:  

Tipo de Token | HTTP Header | Descripción
--------- | --------- | -----------
Connection | x-token | Token asignado a un cliente con credenciales válidas que desea consumir servicios expuestos disponibles para todos, ejemplo Catálogos.
Session | x-token | Token asignado a un usuario con credenciales válidas, que le permitirán ejecutar servicios que por la delicadeza de la información es necesario conocer al responsable de la ejecución, ejemplo: actualización de la información de perfil.
Transaction | x-token | Token creado por un usuario con Sesión válida para la ejecución de servicios que requieren iniciar una transacción para el flujo de un proceso, por ejemplo pagar un servicio.


