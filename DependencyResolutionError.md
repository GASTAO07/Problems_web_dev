
```md
## Installation de dépendances avec npm

**Commande :** `npm install`

```
PS path/to/ratvoyager> npm install
```

**Erreur :**
```
npm ERR! code ERESOLVE
npm ERR! ERESOLVE unable to resolve dependency tree
npm ERR! 
npm ERR! While resolving: ratvoyager@0.0.0
npm ERR! Found: rollup@3.23.0
npm ERR! node_modules/rollup
npm ERR!   dev rollup@"^3.23.0" from the root project
npm ERR! 
npm ERR! Could not resolve dependency:
npm ERR! peer rollup@"^2.0.0" from rollup-plugin-terser@7.0.2     
npm ERR! node_modules/rollup-plugin-terser
npm ERR!   dev rollup-plugin-terser@"^7.0.2" from the root projectnpm ERR! 
npm ERR! Fix the upstream dependency conflict, or retry
npm ERR! this command with --force or --legacy-peer-deps
npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
npm ERR! 
npm ERR! 
npm ERR! For a full report see:
npm ERR! path/to/AppData/Local/npm-cache/_logs/2023-05-27T16_15_29_371Z-eresolve-report.txt

npm ERR! A complete log of this run can be found in: path/to/AppData/Local/npm-cache/_logs/2023-05-27T16_15_29_371Z-debug-0.log
```

**Solution :**
- Mettez à jour la version de "rollup-plugin-terser" pour qu'elle soit compatible avec Rollup version 3.23.0.
  - **Commande :** `npm install rollup-plugin-terser@latest`

- Réduisez la version de Rollup pour qu'elle corresponde à la dépendance requise par "rollup-plugin-terser" (version 2.0.0).
  - **Commande :** `npm install rollup@2.0.0`

- Utilisez le drapeau `--force` ou `--legacy-peer-deps` pour forcer l'installation des dépendances malgré la résolution incorrecte.
  - **Commande :** `npm install --force` ou `npm install --legacy-peer-deps`

## Tentative d'installation avec `--force`

**Commande :** `npm install --force`

```
PS path/to/ratvoyager> npm install --force
```

**Avertissement :**
```
npm WARN using --force Recommended protections disabled.
npm WARN ERESOLVE overriding peer dependency
npm WARN While resolving: rollup-plugin-terser@7.0.2
npm WARN Found: rollup@3.23.0
npm WARN node_modules/rollup
npm WARN   dev rollup@"^3.23.0" from the root project
npm WARN   5 more (@rollup/plugin-commonjs, ...)
npm WARN
npm WARN Could not resolve dependency:
npm WARN peer rollup@"^2.0.0" from rollup-plugin-terser@7.0.2     
npm WARN node_modules/rollup-plugin-terser
npm WARN   dev rollup-plugin-terser@"^7.0.2" from the

 root projectnpm WARN
npm WARN Conflicting peer dependency: rollup@2.79.1
npm WARN node_modules/rollup
npm WARN   peer rollup@"^2.0.0" from rollup-plugin-terser@7.0.2   
npm WARN   node_modules/rollup-plugin-terser
npm WARN     dev rollup-plugin-terser@"^7.0.2" from the root project
npm ERR! code ETARGET
npm ERR! notarget No matching version found for type@module.      
npm ERR! notarget In most cases you or one of your dependencies are requesting
npm ERR! notarget a package version that doesn't exist.

npm ERR! A complete log of this run can be found in: path/to/AppData/Local/npm-cache/_logs/2023-05-27T16_19_57_150Z-debug-0.log
```

**Solution :**
- Supprimez le dossier `node_modules` et le fichier `package-lock.json` pour repartir sur une base propre.
  - **Commande :** `rm -rf node_modules` (pour les systèmes Unix/Linux)
  - **Commande :** `del /s node_modules` (pour Windows)

- Mettez à jour les versions des dépendances dans votre fichier `package.json` pour résoudre manuellement les conflits. Modifiez les versions de `rollup`, `rollup-plugin-terser`, et toutes les autres dépendances concernées pour assurer la compatibilité.
  
- Enregistrez les modifications dans votre fichier `package.json`.

- Exécutez à nouveau la commande `npm install` pour installer les dépendances en fonction du fichier `package.json` mis à jour.
  - **Commande :** `npm install`

Si le problème persiste ou si vous avez besoin d'une assistance supplémentaire, n'hésitez pas à fournir le contenu de votre fichier `package.json` et tout autre journal d'erreur pour une analyse approfondie.
