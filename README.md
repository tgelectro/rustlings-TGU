# rustlings-TGU

variables6.rs

dans le chapitre 1 sur les variables, le programme n'arrivait pas à compiler car le type de variable n'avait pas été défini. j'ai donc simplement précisé le "NUMBER: i32" afin que le programme puisse compiler.

functions5.rs

dans le chapitre 2 sur les fonctions, le problème venait du fait que lee résultat de num * num n'était pas return en fin de programme. j'ai donc retiré le ";" après l'opération afin que le résultat puisse être return.

if3.rs

dans le chapitre 3 sur les conditions, le programme n'arrivait pas à compiler car les "identifier" était attendus en integer mais dans la condition on lui proposait le string "unknown". Sachant que unknown était présent dans la condition suivante dans le cas ou l'identifier serait différent de 1, 2 ou 3, je me suis alors permis de remplacer "unknown" par 4 (j'aurais pu le remplacer par un autre chiffre tant qu'il ne s'agissait pas de 1, 2 ou 3)

primitive_types6.rs

dans le cas présent, il est demandé de récupérer la seconde valeure présente dans le tuple. la position des valeures commençant à 0 il fallait donc récupérer la valeur à l'emplacement 1 du tuple. Pour ce faire on va récupérer la valeure de la façon suivante numbers.1

vecs2.rs

ici il nous est demandé de multiplier par 2 les éléments présent dans le vec possédant le nom "v", il va donc falloir s'y prendre de 2 manières différents. la première manière va être de créer une ligne effectuant le calcul mais sans faire un return direct car le .iter_mut() va se charger de changer les valeurs du vec. la deuxième méthode demande juste de return le résultat de la multiplication par 2 qui va prendre la place de l'ancienne valeur.

move_semantics6.rs

dans ce programme, le code ne peut compiler car la relation d'ownership n'est pas correctement appliquée. En effet la fonction "string_uppercase" devant récupérer l'ownership je commence par supprimer les "&" présente car celle-ci indique que l'on emprunte la valeure à une autre fonction dans le cas présent, puis je met retire également le symbole "&" à la ligne 13 afin de montrer que la fonction possède la variable. Je fais ensuite la procédure inverse avec la fonction "get_char" afin que celle-ci emprunte data à la fonction "string_uppercase".

structs3.rs

dans le cas présent, le code n'est pas terminé et on nous demande de compléter les fonctions qui définiront si notre colis est envoyé à l'international ou non, et à combien vont s'élever les frais d'envoie. dans le cas présent on va faire appel à "&self" car le code étant présent dasn le "impl package", le self fait référence au colis on va donc vérifier si le colis a le même pays d'envoie et de réception et si oui alors le colis n'est pas international, sinon cela signifie qu'il est bien envoyé à l'international. ensuite dans l'autre fonction on va tout simplement faire la multiplication du poids du colis en gramme par le prix de l'envoie par gramme de colis en l'occurence "3 * <poids du colis>".

enums3.rs

dans ce code on va effectuer une énumération des fonctions présentes au dessus, pour ce faire on va leur attribuer une expression à chacune. POur les expression je me suis fié aux "state.process" présents plus bas dans le code afin de les nommer. puis je les aient match avec leur fonction associée, en faisant bien attention de retenir le conseil dans le "TODO:" comme quoi lorsque je fais appel à un tuple j'ai besoin de rajouter des parenthèses (ce qui fût le cas pour le echo et le move_position).

strings4.rs

Dans ce cas on va utiliser les fonctions string et string_slice en fonction de ce que l'on souhaite faire d ela donnée, si on veut récupérer seulement une partie de la chaine de charactères on va utiliser string_slice. En revanche, si on souhaite posséder, créer ou modifier la chaine de charactère.

modules3.rs

dans le cas présent le code ne compilait pas car SystemTime et UNIX_EPOCH n'avait pas été importés dans le code, il a fallut donc en suivant les informations données par l'énoncée, ajouter les deux avec la ligne suivante : use std::time::{SystemTime, UNIX_EPOCH}; .

hashmaps3.rs

Dans le code, il est demandé de rajouter des lignes afin de compter le score entre 2 équipes. on va donc utiliser le hashmap afin de faciliter le stockage des valeurs "goals_scored" et "goals_conceded". on va ensuite effectuer un déréférencement avec le symbole * pour pouvoir modifer les valeurs dans le hashmap.

options3.rs

je n'ai pas directement remarqué car pour moi le code devait s'exécuter normalement, cependant le problème venait du fait que le match y ne prévenait pas qu'il souhaitait récupérer la valeur de la variable créée au-dessus à l'aide de l'esperluette.

generics2.rs

après des recherches je me susi aperçu que pour supporter des résultats de n'importe quel type, il fallait entrer T à la place des u32, à l'aide des erreurs remontées par rust j'ai ensuite ajouté les <T> là ou ils devaient être et le code a pu compiler.

errors6.rs

dans cet exercice, on doit commencer par créer une fonction permettant de bien différencier les parseIntError des CreationErro. Pour ce faire j'ai adapter la fonction from_creation de sortes à  faire la même chose avec la fonction from_parseint. Il a fallut ensuite préciser dans quel cas l'erreur apparait dans la fonction parse_pos_nonzero.

traits5.rs

Dasn ce morceau de code, il est nécessaire d'ajouter impl SomeTrait + OtherTrait, en effet si on ne fait pas ça le compilateur ne sais pas interpréter le type de Item

lifetimes3.rs

dans cet énoncé il nous est demandé d'appliquer les lifetimes aux structs qui sont référencées, j'ai donc appliqué la même chose que pour les exercices précédents mais sur la structure j'ai donc ajouté le <'duree> afin de définir la durée de vie des références, puis je l'ai appliqué à author et title avec le &'duree.

tests4.rs

Ici le code ne compile par car il faut commencer par tester la hauteur et la largeur du rectangle dans les assert_eq! lignes 31 et 32, ensuite, le code n'étant pas dôté de gestion des erreurs il nous manque une réponse en cas d'erreur. C'est à ce moment que l'on va fournir le #[should_panic] afin que les fonctions devant retourner une erreur si le cas se présente puisse provoquer une panique.
