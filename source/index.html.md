---
title: API Reference

language_tabs:
  - shell: cURL

toc_footers:
  - <a href='http://kea.mx'>Documentation Powered by KEA</a>

includes:
  - endpoint
  - acl
  - authentication
  - workflow
  - taxpayer
  - request
  - response
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

We have language bindings in cURL (Shell)! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This API documentation page was created with Slate.
