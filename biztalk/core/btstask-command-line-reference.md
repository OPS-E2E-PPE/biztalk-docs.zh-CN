---
title: BTSTask 命令行参考 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3df365e96c42865189a8e70aa5d1994a4b08a9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357795"
---
# <a name="btstask-command-line-reference"></a><span data-ttu-id="4223c-102">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="4223c-102">BTSTask Command-Line Reference</span></span>
<span data-ttu-id="4223c-103">在本部分中的主题提供附带的 BTSTask 命令行工具的参考信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4223c-103">The topics in this section provide reference information for the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4223c-104">可以使用 BTSTask，如下所示从命令行执行许多应用程序部署任务：</span><span class="sxs-lookup"><span data-stu-id="4223c-104">You can use BTSTask to perform many application deployment tasks from the command line, as follows:</span></span>  
  
- <span data-ttu-id="4223c-105">使用 AddApp 命令添加到 BizTalk 管理数据库的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="4223c-105">Add a BizTalk application to the BizTalk Management database by using the AddApp command.</span></span>  
  
- <span data-ttu-id="4223c-106">使用 AddResource 命令添加到应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="4223c-106">Add an artifact to an application by using the AddResource command.</span></span>  
  
- <span data-ttu-id="4223c-107">使用 ExportApp 命令，应用程序和及其项目导出到某一.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="4223c-107">Export an application and its artifacts to an .msi file by using the ExportApp command.</span></span>  
  
- <span data-ttu-id="4223c-108">使用 ExportBindings 命令可将绑定信息导出到.xml 文件中。</span><span class="sxs-lookup"><span data-stu-id="4223c-108">Export binding information to an .xml file by using the ExportBindings command.</span></span>  
  
- <span data-ttu-id="4223c-109">使用 ImportApp 命令导入的.msi 文件从应用程序。</span><span class="sxs-lookup"><span data-stu-id="4223c-109">Import an application from an .msi file by using the ImportApp command.</span></span>  
  
- <span data-ttu-id="4223c-110">从.xml 文件使用 ImportBindings 命令导入绑定信息。</span><span class="sxs-lookup"><span data-stu-id="4223c-110">Import binding information from an .xml file by using the ImportBindings command.</span></span>  
  
- <span data-ttu-id="4223c-111">列出了通过使用 ListApp 命令及其本地唯一标识符 (Luid) 以及应用程序中包含的项目。</span><span class="sxs-lookup"><span data-stu-id="4223c-111">List the artifacts included in an application along with their locally unique identifiers (LUIDs) by using the ListApp command.</span></span>  
  
- <span data-ttu-id="4223c-112">使用 ListApps 命令列出于 BizTalk 组的 BizTalk 管理数据库中的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="4223c-112">List all applications in the BizTalk Management database for the BizTalk group by using the ListApps command.</span></span>  
  
- <span data-ttu-id="4223c-113">通过使用 ListPackage 命令可列出.msi 文件中的资源。</span><span class="sxs-lookup"><span data-stu-id="4223c-113">List the resources in an .msi file by using the ListPackage command.</span></span>  
  
- <span data-ttu-id="4223c-114">列出所有支持的项目类型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 ListTypes 命令。</span><span class="sxs-lookup"><span data-stu-id="4223c-114">List all of the artifact types supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the ListTypes command.</span></span>  
  
- <span data-ttu-id="4223c-115">使用 RemoveApp 命令可从 BizTalk 管理数据库和 BizTalk 管理控制台中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="4223c-115">Remove an application from the BizTalk Management database and the BizTalk Administration console by using the RemoveApp command.</span></span>  
  
- <span data-ttu-id="4223c-116">使用 RemoveResource 命令从应用程序中删除项目。</span><span class="sxs-lookup"><span data-stu-id="4223c-116">Remove an artifact from an application by using the RemoveResource command.</span></span>  
  
- <span data-ttu-id="4223c-117">使用 UninstallApp 命令从本地计算机中卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="4223c-117">Uninstall an application from the local computer by using the UninstallApp command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4223c-118">不能在将应用程序导入过程中运行的预处理或后处理脚本中使用 BTSTask 命令。</span><span class="sxs-lookup"><span data-stu-id="4223c-118">You cannot use BTSTask commands in a preprocessing or postprocessing script that will run during application import.</span></span> <span data-ttu-id="4223c-119">如果这样做，导入可能会失败。</span><span class="sxs-lookup"><span data-stu-id="4223c-119">If you do, the import may fail.</span></span> <span data-ttu-id="4223c-120">这是因为导入过程中所做的更改看不到脚本。</span><span class="sxs-lookup"><span data-stu-id="4223c-120">This is because changes being made during import are not visible to scripts.</span></span>  
  
 <span data-ttu-id="4223c-121">此外，您可以了解如何为 BTSTask 编辑控制台前景色。</span><span class="sxs-lookup"><span data-stu-id="4223c-121">In addition, you can learn how to edit the console foreground colors for BTSTask.</span></span> <span data-ttu-id="4223c-122">如果控制台背景色为白色，您将难以查看 BTSTask 控制台的输出，并将需要修改控制台前景色。</span><span class="sxs-lookup"><span data-stu-id="4223c-122">If your console background color is white, you will have difficulty reading the BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4223c-123">完成脚本后，它返回零 (0) 以指示成功完成后或一个非零数字来指示失败。</span><span class="sxs-lookup"><span data-stu-id="4223c-123">When a script completes, it returns a zero (0) to indicate successful completion or a non-zero number to indicate failure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4223c-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="4223c-124">In This Section</span></span>  
  
-   [<span data-ttu-id="4223c-125">AddApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-125">AddApp Command</span></span>](../core/addapp-command.md)  
  
-   [<span data-ttu-id="4223c-126">AddResource 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-126">AddResource Command</span></span>](../core/addresource-command.md)  
  
-   [<span data-ttu-id="4223c-127">ExportApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-127">ExportApp Command</span></span>](../core/exportapp-command.md)  
  
-   [<span data-ttu-id="4223c-128">ExportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-128">ExportBindings Command</span></span>](../core/exportbindings-command.md)  

- [<span data-ttu-id="4223c-129">ExportParties 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-129">ExportParties Command</span></span>](../core/exportparties-command.md)

- [<span data-ttu-id="4223c-130">ExportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-130">ExportSettings Command</span></span>](../core/exportsettings-command.md)
  
-   [<span data-ttu-id="4223c-131">ImportApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-131">ImportApp Command</span></span>](../core/importapp-command.md)  
  
-   [<span data-ttu-id="4223c-132">ImportBindings 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-132">ImportBindings Command</span></span>](../core/importbindings-command.md)  

- [<span data-ttu-id="4223c-133">ImportParties 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-133">ImportParties Command</span></span>](../core/importparties-command.md)

- [<span data-ttu-id="4223c-134">ImportSettings 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-134">ImportSettings Command</span></span>](../core/importsettings-command.md)
  
-   [<span data-ttu-id="4223c-135">ListApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-135">ListApp Command</span></span>](../core/listapp-command.md)  
  
-   [<span data-ttu-id="4223c-136">ListApps 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-136">ListApps Command</span></span>](../core/listapps-command.md)  
  
-   [<span data-ttu-id="4223c-137">ListPackage 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-137">ListPackage Command</span></span>](../core/listpackage-command.md)  
  
-   [<span data-ttu-id="4223c-138">ListTypes 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-138">ListTypes Command</span></span>](../core/listtypes-command.md)  
  
-   [<span data-ttu-id="4223c-139">RemoveApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-139">RemoveApp Command</span></span>](../core/removeapp-command.md)  
  
-   [<span data-ttu-id="4223c-140">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-140">RemoveResource Command</span></span>](../core/removeresource-command.md)  
  
-   [<span data-ttu-id="4223c-141">UninstallApp 命令</span><span class="sxs-lookup"><span data-stu-id="4223c-141">UninstallApp Command</span></span>](../core/uninstallapp-command.md)  
  
-   [<span data-ttu-id="4223c-142">如何为 BTSTask 编辑控制台颜色</span><span class="sxs-lookup"><span data-stu-id="4223c-142">How to Edit the Console Colors for BTSTask</span></span>](../core/how-to-edit-the-console-colors-for-btstask.md)