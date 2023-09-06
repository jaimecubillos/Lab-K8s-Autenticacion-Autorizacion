# REQUERIMIENTOS

## PARTE 1 - REPASO CONCEPTOS BASICOS
Crear un deployment con el nombre *cloudcamp1* con las siguientes especificaciones:

- Image: nginx:1.14.2
* replicas: 2
+ namespace: colombia
- container name: finanzas
* tags environment: stg, location: colombia
+ service account: finanzas-sa
- Crear el secreto passwordbd con el valor #61!.9sg&)/%8
* Montar el secreto *passwordbd* como volumen

Copiar el valor del secretto del secreto *passwordbd* en la path $HOME/lab-autentication-autorizacion/secreto

## PARTE 2 - SERVICE ACCOUNT
Crear un deployment con el nombre *cloudcamp2* con las siguientes especificaciones:

- Image: redis:latest
* replicas: 2
+ namespace: brasil
- container name: mercadeo
* tags environment: stg, location: brasil
+ service account: mercadeo-sa
- Deshabilitar el automando del token de los service account unicamente a nivel de deployment *cloudcamp2*

Copiar el valor del token del service account *mercadeo* en la path $HOME/lab-autentication-autorizacion/token-sa

## PARTE 3 - RBAC

Por medio de Roles o CLusterRoles con sus respectivos Bindings otorgar los siguientes permisos, así:

- Otorgar permisos de "get", "list", "create" a los secrets y deployments del namespace finanzas para el service account finanzas-sa
* Agregar el usuario operatornet in the currect kubeconfig value
+ Otorgar permisos de "delete", "create" a los networkpolicies para el usuario operatornet en todos los namespaces
- Otorgar permisos de "get", a los "pods" y los "pod/logs" del namespace mercadeo para el service account finanzas-sa


# TIPS

- Deshabilitar el automontado del token del service account en el manifiesto del deployment y/o pod y no a nivel de serviceaccount
- Validar por medio kubectl auth can-i que los permisos RBAC fueron otorgados satisfactoriamente

