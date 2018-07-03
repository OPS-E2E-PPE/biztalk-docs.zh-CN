---
title: 更新应用程序的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 072eaf25-a1ee-4af3-b034-525a04260ef4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75dbde61369cdc8658dd9b39fa75fe2655225222
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001726"
---
# <a name="best-practices-for-updating-applications"></a>更新应用程序的最佳实践
本主题介绍你应考虑使用更新 BizTalk 应用程序和项目时的最佳做法。  
  
## <a name="versioning"></a>版本控制  
 **实现版本控制策略**  
  
- 如果长时间运行，则使用事务或 BizTalk 应用程序无法创建向下，若要执行升级或 bug 修复，很好的版本控制策略至关重要。 应计划的所有 BizTalk 项目的版本控制策略： 架构、 映射、 自定义适配器、 管道、 管道组件、 业务流程、 业务规则、 BAM 和自定义类名为在业务流程和映射。  
  
  **与 BizTalk 管理数据库和全局程序集缓存 (GAC) 中的程序集匹配**  
  
- 确保程序集的相同版本并在 BizTalk 管理数据库和 GAC 中，以便你的应用程序正常运行。 如果部署程序集时并不总是将其安装到 GAC 中，GAC 和 BizTalk 管理数据库中的程序集版本可能有所不同，从而导致运行时出现处理错误。  
  
  **使用 BizTalk 程序集检查器和远程 GAC 工具验证版本控制**  
  
- **BizTalk 程序集检查器和远程 GAC 工具**(BTSAssemblyChecker.exe) 会检查部署到 BizTalk 管理数据库的程序集的版本，并验证它们都正确注册所有 BizTalk 上的 GAC 中服务器的计算机。 可以使用此工具检查 BizTalk 的所有节点上已安装了所有包含的某一 BizTalk 应用程序的项目的程序集。 该工具是结合 solid 版本控制策略来验证一组程序集的正确版本上安装了每个 BizTalk 计算机，尤其是使用通过并行部署方法时特别有用。  
  
- 该工具随 BizTalk Server 安装介质上 Support\Tools\x86\BTSAssemblyChecker.exe。  
  
  **使用版本控制产品**  
  
- 版本控制产品，如 Microsoft Visual Studio® Team Foundation Server 2010，应该用于跟踪和版本控制 BizTalk 项目。 有关 Microsoft Visual Studio® Team Foundation Server 2010 的详细信息请参阅[Microsoft Visual Studio® Team Foundation Server 2010](http://go.microsoft.com/fwlink/?LinkId=210637) (http://go.microsoft.com/fwlink/?LinkId=210637)  
  
  **到多个 BizTalk 应用程序的身份项目**  
  
- 若要执行的 BizTalk 项目的程序集版本控制，您的 BizTalk 解决方案程序集需要考虑 （打包） 的方式以允许 BizTalk Server 版本控制。 分解的详细信息，请参阅[将项目添加到应用程序](../technical-guides/adding-artifacts-to-an-application.md)。  
  
## <a name="updating-an-application"></a>更新应用程序  
 **使用.msi 文件将更新的应用程序**  
  
-   升级应用程序通常是一个故意安排和精确的操作，在生产环境中。 当你升级应用程序时，你通常应使用手动检查表。 但是，您可能能够通过使用.msi 文件，来优化某些步骤。 当您使用某一.msi 文件时，可以总结你的应用程序项目打包到可分发包。 向多个运行时中推出更新的 Dll 或执行组级别部署时，某一.msi 文件是特别有用。 在创建某一.msi 文件时，应从包中排除所有其他未更改的资源和绑定。  
  
-   如果更新 BizTalk 程序集，您应停止、 取消登记、 重新登记，并启动 BizTalk 项目手动之前和之后导入和安装.msi 文件。 有关更新的 BizTalk 程序集的详细信息，请参阅[清单： 更新的程序集](../technical-guides/checklist-updating-an-assembly.md)。  
  
-   如果升级 BizTalk Server 程序集的并行版本控制，您将必须使用.msi 文件之前和之后执行手动步骤。 有关所需的手动步骤的详细信息，请参阅[清单： 更新应用程序使用的并行版本控制](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)。  
  
## <a name="updating-an-assembly"></a>更新的程序集  
 **增加在生产环境中的程序集的版本号**  
  
- 如果要更新在生产环境中运行的程序集，您应始终是递增程序集的版本号。  
  
  **使用更新的程序集更新 GAC**  
  
- 当更新包含业务流程、 架构或映射的程序集时，必须使用包含新版本的程序集更新 gac。 否则，BizTalk Server 将使用版本已过时。 要执行此操作，请在运行应用程序绑定到的主机的实例的每台计算机上，从 GAC 卸载包含更新项目的程序集的过期版本，并确保安装新版本。  
  
  **更新的程序集后重新启动主机实例**  
  
- 如果更新现有应用程序中的 BizTalk 程序集时，可能需要重新启动主机实例以使更改生效。 重新启动主机实例停止所有主机实例运行其他应用程序。  
  
## <a name="updating-an-artifact"></a>更新某一项目  
 **取消部署依赖的程序集的项目，这取决于之前**  
  
- 如果要取消部署被另一个项目所依赖的项目，您必须首先取消部署依赖的程序集。  
  
  > [!NOTE]  
  >  如果你不执行第一次取消依赖的程序集的部署，在 BizTalk Server 管理控制台将显示一条警告，并防止错误的顺序取消部署项目。  
  
  **不会停止其他应用程序依赖的项目**  
  
- 如果您停止一个应用程序中另一个应用程序所依赖的项目（这可能导致停止整个应用程序），则依赖的应用程序将无法正常工作。 有关停止应用程序的详细信息，请参阅[如何启动和停止 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。  
  
  **添加对程序集之前移动项目的引用**  
  
- 将项目移向新应用程序时，该项目所依赖的其他所有项目也会被移动，除非此新应用程序有对包含移动项目所依赖项目的应用程序的引用。 同样，依赖于移动项目的所有项目也会被移动，除非包含这些项目的应用程序有对新应用程序的引用。 当移动项目，将显示一起移动的其他项目的列表。  
  
## <a name="updating-bindings"></a>更新绑定  
 **自动执行重新配置绑定**  
  
-   在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。 可以使用绑定文件来自动化此过程。 如果要更新的程序集相同的版本，可以首先导出绑定文件的程序集，然后更新程序集，然后导入应用程序，该程序集并导入绑定文件，然后重新应用以前的绑定。 如果要使用更新的版本更新程序集，可以导出绑定文件，编辑该文件以反映新的程序集版本、 新的程序集导入应用程序，然后通过导入绑定文件中应用的新绑定。 有关绑定文件的详细信息，请参阅[如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](http://go.microsoft.com/fwlink/?LinkID=155000)(http://go.microsoft.com/fwlink/?LinkID=155000)。  
  
## <a name="starting-or-stopping-an-application"></a>启动或停止应用程序  
 **停止应用程序来更新项目**  
  
-   如果不停止应用程序更新应用程序中的项目，需要暂时禁用终结点，通过来暂停进程发布到 MessageBox 数据库和停止并取消登记任何正在运行的实例。 若要停止并取消登记正在运行的实例，所有已冻结或挂起的实例必须进行手动恢复，已完成，或者终止。  
  
-   尽管它不需要停止应用程序，以便更新某个项目或安装应用程序，但我们建议你更新项目时始终停止应用程序。  
  
## <a name="see-also"></a>请参阅  
 [如何将绑定导出到绑定文件](../technical-guides/how-to-export-bindings-to-a-binding-file.md)