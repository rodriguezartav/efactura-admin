BUILD SPEC FOR LAMBDA FUNCTIONS
# lamba-edge_html
# step-efactura-rds-notify


{"documentoId": 2,"account": "rodco","cedula": "3102755909"}

{ "documentoId": 1,"account": "rodco","cedula": "3102755909,"cedulaS3": "3102755909_staging" }

sls invoke local -f step-send --data '{"documentoId":1,"account":"rodco","cedula":"3102999999","cedulaS3":"3102755909_staging","key":"facturas/3102755909_staging/50610091800310275590900100001010000000001112345678.xml","id":2,"environment":"staging","createdBy":null,"updatedBy":null,"createdAt":"2018-09-10 17:23:35","updatedAt":"2018-09-10 17:23:35","namespaceId":"seed","username":"cpj-3-102-755909@stag.comprobanteselectronicos.go.cr","password":"*l@ko@)fp=(wQ:V:g;*c","ubicacion":"6,07,02","email":"3102999999@efactura.io","name":"Positive ION SRL","pin":"0531","telefono":"22222222","consecutivoFactura":0,"consecutivoNotaCredito":0,"consecutivoNotaDebito":0,"certificado":"3102755909_staging/pionstaging.p12","documentoClave":"50610091800310275590900100001010000000001112345678","emisor":{"Nombre":"Positive ION SRL","Identificacion":{"Tipo":"02","Numero":"3102755909"},"Ubicacion":{"Provincia":"6","Canton":"07","Distrito":"02","Barrio":"01","OtrasSenas":"Costa Rica"},"Telefono":{"CodigoPais":"506","NumTelefono":"22222222"},"CorreoElectronico":"3102755909@efactura.io"},"receptor":{"Nombre":"ACUÑA Y HERNANDEZ S.A","Identificacion":{"Tipo":"02","Numero":"3101085172"}}}'

sls invoke local -f step-check --data '{"documentoClave":"50610091800310275590900100001010000000001112345678","cedula":"3102999999","cedulaS3":"3102755909_staging","username":"cpj-3-102-755909@stag.comprobanteselectronicos.go.cr","password":"*l@ko@)fp=(wQ:V:g;*c","documentoId":1}'

sls invoke local -f step-notify --data '{"documentoClave":"50610091800310275590900100001010000000001112345678","documentoId":1,"cedula":"3102999999","cedulaS3":"3102755909_staging"}'# step-efactura-receive
# efactura-admin
