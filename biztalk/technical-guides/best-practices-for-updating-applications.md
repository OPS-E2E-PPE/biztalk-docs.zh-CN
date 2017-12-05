---
title: "更新应用程序的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 072eaf25-a1ee-4af3-b034-525a04260ef4
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01cf54454866eadbd70de7ef30439a0e7068cb1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="best-practices-for-updating-applications"></a>更新应用程序的最佳做法
本主题介绍你应考虑使用更新 BizTalk 应用程序和项目时的最佳做法。  
  
## <a name="versioning"></a>版本控制  
 **实施版本控制策略**  
  
-   如果长时间运行，则使用事务或 BizTalk 应用程序不能被移除执行升级或 bug 修复，良好的版本控制策略至关重要。 你应该规划所有 BizTalk 项目的版本控制策略： 架构、 映射、 自定义适配器、 管道、 管道组件、 业务流程、 业务规则、 BAM 和自定义类调用中业务流程和映射。  
  
 **匹配 BizTalk 管理数据库和全局程序集缓存 (GAC) 中的程序集**  
  
-   以便你的应用程序工作正常，请确保相同版本的程序集位于 GAC 中，如 BizTalk 管理数据库。 如果部署程序集时并不总是将其安装到 GAC 中，GAC 和 BizTalk 管理数据库中的程序集版本可能有所不同，从而导致运行时出现处理错误。  
  
 **使用 BizTalk 程序集检查和远程 GAC 工具验证版本控制**  
  
-   **BizTalk 程序集检查器和远程 GAC 工具**(BTSAssemblyChecker.exe) 检查部署到 BizTalk 管理数据库中的程序集的版本，并验证它们是否正确注册所有 BizTalk 上的 GAC 中服务器的计算机。 此工具可用于验证包含某些 BizTalk 应用程序的项目的所有程序集安装在所有 BizTalk 节点。 该工具是结合稳定版本控制策略以验证一组程序集的正确版本上安装了每个 BizTalk 机，尤其是使用通过并行部署方法时特别有用。  
  
-   该工具时使用的 BizTalk Server 安装媒体上 Support\Tools\x86\BTSAssemblyChecker.exe。  
  
 **使用版本控制产品**  
  
-   应将版本控制产品，如 Microsoft Visual Studio® Team Foundation Server 2010，用于跟踪和版本管理 BizTalk 项目中。 有关 Microsoft Visual Studio® Team Foundation Server 2010 的详细信息请参阅[Microsoft Visual Studio® Team Foundation Server 2010](http://go.microsoft.com/fwlink/?LinkId=210637) (http://go.microsoft.com/fwlink/?LinkId=210637)  
  
 **到多个 BizTalk 应用程序的因素项目**  
  
-   若要执行的 BizTalk 项目的程序集版本控制，BizTalk 解决方案程序集需要包含 （打包） 的方式以便 BizTalk Server 版本控制。 有关将分解的详细信息，请参阅[将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)。  
  
## <a name="updating-an-application"></a>更新应用程序  
 **使用.msi 文件更新的应用程序**  
  
-   升级应用程序通常是一种有意和精确的操作，在生产环境中。 当你升级应用程序时，你通常应使用手动检查列表。 但是，你可能能够通过使用.msi 文件，来优化某些步骤。 当使用.msi 文件时，你可以完成可再发行包到你应用程序的项目。 到多个运行时框推出更新的 Dll 或执行组级别部署时，则.msi 文件是特别有用。 当你创建一个.msi 文件时，则应从包中排除所有其他不变的资源和绑定。  
  
-   如果你更新 BizTalk 程序集，应停止、 取消、 重新登记，然后之前和之后导入并安装.msi 文件手动启动 BizTalk 项目。 有关更新 BizTalk 程序集的详细信息，请参阅[清单： 更新程序集](../technical-guides/checklist-updating-an-assembly.md)。  
  
-   如果升级使用的并行版本控制的 BizTalk Server 程序集，你将需要使用.msi 文件之前和之后执行手动步骤。 有关手动步骤，所需的详细信息，请参阅[清单： 更新应用程序使用的并行版本控制](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)。  
  
## <a name="updating-an-assembly"></a>更新程序集  
 **增加的生产环境中的程序集的版本号**  
  
-   如果正在更新生产环境中运行的程序集，你应该始终增加程序集版本号。  
  
 **使用更新的程序集中更新 GAC**  
  
-   在更新包含业务流程、 架构或映射的程序集时，你必须使用包含新版本的程序集更新 gac。 否则，BizTalk Server 将使用过时的版本。 要执行此操作，请在运行应用程序绑定到的主机的实例的每台计算机上，从 GAC 卸载包含更新项目的程序集的过期版本，并确保安装新版本。  
  
 **在更新程序集后重新启动主机实例**  
  
-   如果现有应用程序中的 BizTalk 程序集进行了更新，你可能需要重新启动主机实例以使更改生效。 重新启动主机实例将停止所有主机实例运行其他应用程序。  
  
## <a name="updating-an-artifact"></a>更新某个项目  
 **取消部署的项目，它依赖于前一个依赖项目**  
  
-   如果你取消部署另一个项目所依赖的项目，你必须首先取消部署依赖项目。  
  
    > [!NOTE]  
    >  如果你不执行第一次取消依赖项目的部署，则 BizTalk Server 管理控制台将显示一条警告，并阻止你从正在取消部署项目顺序不正确。  
  
 **不会停止依赖于另一个应用程序的项目**  
  
-   如果您停止一个应用程序中另一个应用程序所依赖的项目（这可能导致停止整个应用程序），则依赖的应用程序将无法正常工作。 要停止应用程序的详细信息，请参阅[如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。  
  
 **添加对之前移动项目程序集的引用**  
  
-   将项目移向新应用程序时，该项目所依赖的其他所有项目也会被移动，除非此新应用程序有对包含移动项目所依赖项目的应用程序的引用。 同样，依赖于移动项目的所有项目也会被移动，除非包含这些项目的应用程序有对新应用程序的引用。 当移动项目，你会看到的其他项目，也将被移动的列表。  
  
## <a name="updating-bindings"></a>更新绑定  
 **自动执行绑定的重新配置**  
  
-   在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。 可以通过使用绑定文件来自动执行此过程。 如果你要更新相同版本的程序集，首先将绑定文件导出为程序集，然后可以更新该程序集，然后将程序集导入到该应用程序，并导入绑定文件，然后重新应用以前的绑定。 如果你使用较新版本进行更新程序集，你可以导出绑定文件，编辑该文件以反映新的程序集版本，将新的程序集导入到该应用程序，然后将新的绑定应用通过导入绑定文件。 有关绑定文件的详细信息，请参阅[如何导出绑定到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkID=155000)(http://go.microsoft.com/fwlink/?LinkID=155000)。  
  
## <a name="starting-or-stopping-an-application"></a>启动或停止应用程序  
 **停止应用程序更新项目**  
  
-   如果不停止应用程序更新应用程序中的项目，你需要暂时暂停发布到 MessageBox 数据库通过禁用终结点，并停止并取消任何正在运行的实例。 若要停止并取消正在运行的实例，所有的已冻结或挂起实例必须使用方法手动恢复和完成，或终止。  
  
-   尽管无需停止应用程序，以便更新项目，或安装应用程序，但是我们建议你始终停止应用程序，当你更新项目。  
  
## <a name="see-also"></a>另请参阅  
 [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)