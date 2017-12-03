---
title: "Mithilfe von Visual Studio-Tools für Docker (Visual Studio unter Windows)"
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7a24633f5857bc5b72ebab42020627c645f4302
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="be6bd-104">Mithilfe von Visual Studio-Tools für Docker (Visual Studio unter Windows)</span><span class="sxs-lookup"><span data-stu-id="be6bd-104">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="be6bd-105">Der Workflow Entwickler bei Verwendung von Visual Studio-Tools für Docker ähnlich wie der Workflow wird bei Verwendung von Visual Studio-Code und Docker-Befehlszeilenschnittstelle (in der Tat basiert auf der gleichen Docker-Befehlszeilenschnittstelle), aber es ist einfacher, um zu beginnen, vereinfacht den Prozess und höhere Steigerung der Produktivität für den Build ausführen und Aufgaben zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="be6bd-105">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="be6bd-106">Es kann auch zum Ausführen und Debuggen der Container über einfache Aktionen wie z. B. F5 bzw. STRG + F5 in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="be6bd-106">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="be6bd-107">Sogar noch stärker mit Visual Studio 2017 und zum Ausführen und Debuggen von einem einzelnen Container kann zusätzlich dazu können auch ausführen und Debuggen eine Gruppe von Containern (betreffender) zur gleichen Zeit, wenn sie in der gleichen Docker compose.yml-Datei auf Projektmappenebene definiert sind.</span><span class="sxs-lookup"><span data-stu-id="be6bd-107">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="be6bd-108">Konfigurieren der lokalen Umgebung</span><span class="sxs-lookup"><span data-stu-id="be6bd-108">Configuring your local environment</span></span>

<span data-ttu-id="be6bd-109">Mit den neuesten Versionen von Docker für Windows ist es einfacher, die jemals zum Docker-Anwendungen entwickeln, da das Setup einfach ist, ist, wie in den folgenden Ressourcen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="be6bd-109">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="be6bd-110">**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Installieren von Docker für Windows <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="be6bd-110">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="be6bd-111">Wenn Sie Visual Studio 2015 verwenden, müssen Sie Update 3 oder höher sowie Visual Studio-Tools für Docker verfügen.</span><span class="sxs-lookup"><span data-stu-id="be6bd-111">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="be6bd-112">**Weitere Informationen:** finden Sie Anweisungen zum Installieren von Visual Studio [https://www.visualstudio.com/ \ Produkte/Visual Studio-2015-Produkt-Editionen](https://www.visualstudio.com/products/vs-2015-product-editions).</span><span class="sxs-lookup"><span data-stu-id="be6bd-112">**More info:** For instructions on installing Visual Studio, go to [https://www.visualstudio.com/\ products/vs-2015-product-editions](https://www.visualstudio.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="be6bd-113">Um weitere Informationen zum Installieren von Visual Studio-Tools für Docker anzuzeigen, wechseln Sie zu <http://aka.ms/vstoolsfordocker> und <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span><span class="sxs-lookup"><span data-stu-id="be6bd-113">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="be6bd-114">Wenn Sie Visual Studio 2017 verwenden, wird Unterstützung für Docker bereits verwendet.</span><span class="sxs-lookup"><span data-stu-id="be6bd-114">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="be6bd-115">Mithilfe von Docker-Tools in Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="be6bd-115">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="be6bd-116">Visual Studio-Tools für Docker bietet eine einheitliche Methode zum Entwickeln und überprüfen Sie lokal die Docker-Container für Linux in einem Linux-Docker-Host oder virtuellen Computer oder Ihrer Windows-Container direkt unter Windows.</span><span class="sxs-lookup"><span data-stu-id="be6bd-116">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="be6bd-117">Wenn Sie einen einzelnen Container verwenden, werden im ersten Schritt müssen Sie beginnen Docker-Unterstützung in Ihr Projekt .NET Core zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="be6bd-117">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="be6bd-118">Zu diesem Zweck das Kontextmenü der Projektdatei, wie in Abbildung 4-25 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="be6bd-118">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/Image/File/205468/1/Add-docker-Support.PNG](./media/image31.png)

<span data-ttu-id="be6bd-120">Abbildung 4-25: das Aktivieren der Docker-Unterstützung für Visual Studio-Projekts</span><span class="sxs-lookup"><span data-stu-id="be6bd-120">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="be6bd-121">Verwenden von Docker-Tools in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="be6bd-121">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="be6bd-122">Beim Hinzufügen Docker-Unterstützung zu einem Service-Projekt in der Projektmappe (siehe Abbildung 4-26), Visual Studio ist nicht einfach eine DockerFile-Datei dem Projekt hinzufügen, es ist auch ein Abschnitt "Dienst" in der Projektmappe Docker compose.yml-Dateien (oder erstellen die Dateien aus, wenn sie nicht hinzufügen vorhanden sein).</span><span class="sxs-lookup"><span data-stu-id="be6bd-122">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="be6bd-123">Es ist eine einfache Möglichkeit zum Verfassen von multicontainer Projektmappe zu beginnen. Anschließend können Sie die Docker-compose.yml-Dateien öffnen und mit zusätzlichen Funktionen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="be6bd-123">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="be6bd-124">Abbildung 4-26: das Aktivieren der Unterstützung von Docker-Lösung in einem 2017 von Visual Studio-Projekt</span><span class="sxs-lookup"><span data-stu-id="be6bd-124">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="be6bd-125">Die dockerfile-Datei von dieser Aktion nicht nur dem Projekt hinzugefügt, werden außerdem die erforderliche Konfiguration Codezeilen hinzugefügt, um eine globale Docker compose.yml auf Projektmappenebene festgelegt.</span><span class="sxs-lookup"><span data-stu-id="be6bd-125">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="be6bd-126">Sie können auch Docker-Unterstützung aktivieren beim Erstellen einer ASP.NET Core-Projekts in Visual Studio-2017, wie in Abbildung 4-27 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="be6bd-126">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="be6bd-127">Abbildung 4-27: das Aktivieren der Docker Unterstützung beim Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="be6bd-127">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="be6bd-128">Nachdem Sie die Projektmappe in Visual Studio Docker-Unterstützung hinzugefügt haben, sehen Sie auch mit den hinzugefügten Docker-compose.yml-Dateien im Projektmappen-Explorer eine neue Knotenstruktur, wie in Abbildung 4-28 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="be6bd-128">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="be6bd-129">Abbildung 4-28: Docker compose.yml Dateien zeigen jetzt im Projektmappen-Explorer</span><span class="sxs-lookup"><span data-stu-id="be6bd-129">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="be6bd-130">Sie können die Bereitstellung einer Multicontainer-Anwendung unter Verwendung einer einzelnen Docker-compose.yml beim Ausführen von Docker ergeben. Allerdings fügt Visual Studio eine Gruppe, damit Sie, abhängig von der Umgebung (Entwicklung im Vergleich zur Produktion) und die Ausführung der überschreiben können Typ (Version im Vergleich zu Debug).</span><span class="sxs-lookup"><span data-stu-id="be6bd-130">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="be6bd-131">Diese Funktion wird in den Kapiteln besser erklärt werden.</span><span class="sxs-lookup"><span data-stu-id="be6bd-131">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="be6bd-132">**Weitere Informationen:** Detailinformationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, lesen Sie die folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="be6bd-132">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="be6bd-133">Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="be6bd-133">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="be6bd-134">Stellen Sie einen ASP.NET Container bereit, mit einem Docker-Remotehost: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="be6bd-134">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="be6bd-135">[Vorherigen] (Docker-apps-Inner-Schleife-workflow.md) [weiter] (Set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="be6bd-135">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>