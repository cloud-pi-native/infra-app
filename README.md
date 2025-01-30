
# infra-app

En cours de construction : Application deployé par l'infra

## Description

infra-app est un projet permettant le déploiement d'applications par l'infrastructure Cloud Pi Native sur des clusters Openshift, OKD ou Kubernetes.

## Fonctionnement

Ce projet regroupe les applications déployées par l'infrastructure et utilise ArgoCD pour automatiser leur déploiement. Le déploiement est géré à l'aide de fichiers de configuration situés dans le répertoire unmanaged.

Chaque application est déployée sur l'ensemble des clusters conformes à la nomenclature définie. Le système prend en charge la gestion dynamique des clusters et des applications, permettant ainsi une scalabilité et une flexibilité accrues.

## Déploiement

Pour déployer une application, il suffit d'adapter le fichier situé dans unmanaged selon les besoins.
Le fichier unmanaged est un ApplicationSet d'ArgoCD qui permet de générer dynamiquement des applications ArgoCD en fonction des fichiers de valeurs propres à chaque cluster.

Les valeurs YAML doivent respecter la structure définie dans les fichiers existants pour assurer un déploiement cohérent sur l'ensemble des clusters.

## Nomenclature des clusters

Le déploiement fonctionne selon une nomenclature stricte des clusters. Chaque cluster doit suivre la convention de nommage définie dans cluster-automation. Cela garantit que toutes les applications sont déployées de manière cohérente et sans erreur.

Stratégie de Synchronisation

Le système de synchronisation intègre plusieurs options :

AutoSync : Permet de synchroniser automatiquement les applications lorsqu'une modification est détectée.

SelfHeal : Assure que l'état des applications reste conforme à celui défini dans Git.

Prune : Supprime les ressources obsolètes lorsque nécessaire.

ServerSideApply : Utilise une approche serveur pour appliquer les changements de manière plus efficace.

## Conclusion

Ce projet permet de déployer automatiquement des applications sur plusieurs clusters en adaptant simplement les fichiers de configuration. Il repose sur ArgoCD, Helm, et une structure de répertoires bien définie pour assurer une gestion efficace des applications Cloud Pi Native.

## Points Clés :

Déploiement automatique sur plusieurs clusters

Utilisation d'ApplicationSet et Helm

Gestion centralisée via GitOps

Synchronisation et auto-réparation des applications

Supporte l'ajout de nouveaux clusters et applications dynamiquement

Pour toute modification ou ajout d'une application, il suffit d'éditer les fichiers de valeurs et de suivre la nomenclature définie. Une validation des fichiers YAML est recommandée avant le déploiement pour éviter les erreurs.