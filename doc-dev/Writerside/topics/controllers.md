# Controllers

> Les controllers sont des class permettant d'éffectuer les actions de traitement à l'accès de liens précis.

Ils sont situés par défaut dans le dossier <code>Src/Controllers</code> sous la méthode de chargement <code>psr-4</code>.

## Définition

Créer une classe dans le dossier des controllers qui **extends** de la class <code>CustomController</code>. 
Cette classe sert d'intermédiaire entre le framework et l'utilisateur.

<code-block lang="php">
&lt;?php

namespace Controllers;

use EagleCore\Routing\Response\BladeResponse;
use EagleCore\Routing\Response\JsonResponse;
use EagleCore\Routing\Request\Request;

class MyController extends CustomController{
    public function showHomePage():BladeResponse{
        return new BladeResponse(pathFromViews: "eagle",datas: ["websiteLink" => "https://yahvya.github.io/eagle-final-doc/"]);
    }

    public function getDatasOf(Request $requestManager,string $username):JsonResponse{
        return new JsonResponse(json: ["method" => $requestManager->getMethod(),"username" => $username]);
    }
}
</code-block> 

## Utilisation

Les controllers peuvent être associés aux liens dans la définition des routes

<code-block lang="php">
&lt;?php

use Controllers\MyController;
use EagleCore\Routing\Routes\Route;
use EagleCore\Routing\Routes\RouteManager;

RouteManager::registerRoute(
    route: Route::get(
        link: "/",
        toExecute: [MyController::class,"showHomePage"]),
        routeName: "app.home"
    )
);

RouteManager::registerRoute(
    route: Route::get(
        link: "/datas/:username",
        toExecute: [MyController::class,"getDatasOf"]),
        routeName: "app.get-datas"
    )
);
</code-block>

## Fonctions par défaut

> La class d'héritage des controllers sert actuellement de marqueur et n'embarque pas de fonctions par défaut

## Ajouter des fonctions

> La classe intermédiaire <code>CustomController</code> permet à l'utilisateur d'apporter des customisations à ses controllers, les méthodes ajoutées sont héritées des controllers.
