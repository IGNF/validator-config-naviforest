# Principales commandes

Voir l'aide en mode console :

```
bin/console list ign_validator
```

# Configurations du validateur

Les commandes permettent les conversions entre les 3 formats de configuration

- Configuration en CSV ( validator-config-cnig/config-backup )

- Base de données ( consultation et l'édition via l'interface : <gpu-site>/admin/validator/ )

- Configuration XML : utilisée par le validator ( validator-config-cnig/config )

```
        restore             
     ------------->        export
 CSV                BDD  ------------->  XML
     <-------------     
         backup 
```

Remarque : La commande import, symétrique à export, existe; mais peut perdre des informations (en particulier l'héritage)


# Processus de base pour modifier la configuration du validateur

1. Importer la configuration

Mettre à jour la configuration actuelle
```
bin/console ign_validator:config:restore --mode update
```

Ecraser la configuration actuelle
```
bin/console ign_validator:config:restore --mode replace
```

2. Modifier la configuration à l'aide de l'interface

L'interface permet de modifier les différents aspects

3. Sauvegarder la nouvelle configuration

```
bin/console ign_validator:config:backup
```

4. Exporter la nouvelle configuration pour le validateur

```
bin/console ign_validator:config:export
```

5. Commiter et pusher la nouvelle configuration
