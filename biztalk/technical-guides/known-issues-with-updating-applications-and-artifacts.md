---
title: "带有更新应用程序和项目的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ea03c-d453-40cc-8ddb-18a96f8ddfe5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e445ef19a1d65cc97a3603492a1ad9ba0442e9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-updating-applications-and-artifacts"></a>更新应用程序和项目的已知的问题
## <a name="updating-an-application"></a>更新应用程序  
 **删除或删除项目不会删除它从所有位置**  
  
 从 BizTalk Server 数据库移除或删除项目，使之不再显示在管理控制台中或由 BTSTask ListApp 命令生成的应用程序的项目列表中。 它不会如果它存在于其中任何位置的从 Windows 注册表、 全局程序集缓存 (GAC)、 虚拟目录或文件系统中，删除项目。 如果是只存在于 BizTalk 管理数据库中的发送端口、发送端口组、接收端口和接收位置，此操作将完全删除项目。  
  
## <a name="updating-an-artifact"></a>更新某个项目  
 **删除或更改项目的状态可能会导致应用程序无法正常工作**  
  
 如果您从到另一个应用程序中添加的引用，并对在其另一个应用程序依赖，或删除项目的项目的状态进行任何更改，应用程序具有依赖关系将无法正常运行。 有关更改项目的状态的详细信息，请参阅部分中相应项目[管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。  
  
 **不支持.NET 策略文件**  
  
 BizTalk Server 中不支持的.NET 策略文件使用。 原因在于策略文件可能不会以预期方式工作。 策略文件将.NET 重定向到指定的程序集版本在 GAC 中，但[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常从缓存或 BizTalk 管理数据库中访问程序集和项目数据。 策略文件可能不会执行预期操作，具体情况视项目类型、缓存情况和主机实例是否重新启动而定。  
  
## <a name="updating-an-assembly"></a>更新程序集  
 **程序集的更改可能会生效，如果主机未停止**  
  
 BizTalk 程序集必须遵循.NET 版本控制规则。 其主要含义是：根据特定版本的其他 .NET 项目或程序集（包括 BizTalk 项目）生成 BizTalk 项目后，该 BizTalk 项目将继续使用该版本，直到根据更高的版本重新生成该 BizTalk 项目。  
  
 如果在没有停止和启动加载类型的 BizTalk 主机实例的情况下，没有更改 BizTalk 项目上的版本号而重新部署了程序集，则在进行与 .NET 版本控制有关的开发过程中会出现一个常见问题。  
  
 再次运行该进程时，更改不会生效。 这是由 .NET 程序集加载到内存中的方式造成的。 主机已有的程序集的内存中副本，因为它不会不时重新加载程序集的新副本将放入全局程序集缓存 (GAC)。 例如，部署并运行带有业务流程的版本 1.0.0.0 的程序集，如果对业务流程进行了更改而未更改版本号，则这些更改不会生效。 停止主机实例后将释放该程序集的内存中副本，重新启动该主机实例时，将重新加载该程序集的新副本并获取更改。 如果已部署的新版本，例如版本 2.0.0.0，和它加载时，则所做的更改将生效。  
  
 **更改程序集版本可能会破坏程序集和引用该版本的项之间的关系**  
  
 在.NET Framework 开发很常见的做法进行生成时，更新的程序集版本号为当前的生成号。 但在开发 BizTalk 解决方案时，更改程序集版本号会中断程序集与通过其程序集版本号引用 DLL 的依赖项之间的关系。 下表列出了通过使用其版本号和更改程序集版本号的效果引用的 BizTalk Server 程序集的项。  
  
|实体|更改程序集版本号的影响|  
|------------|------------------------------------------------|  
|绑定文件|更改程序集版本号会导致引用该程序集的所有现有绑定文件失败。 这是因为绑定文件通过包括版本号在内的属性来引用程序集。<br /><br /> 可以使用记事本或其他编辑器更新绑定文件中的版本信息。 你可以还重新部署解决方案，并使用 BizTalk Server 管理控制台，然后重新生成绑定文件。 最后，可以使用脚本来进行自动化部署和版本控制。 有关部署的详细信息，请参阅[部署和管理 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154210)(http://go.microsoft.com/fwlink/?LinkID=154210)。|  
|BAM 跟踪配置文件定义 (.btt) 文件|更改程序集版本号会导致所有现有 BAM 跟踪配置文件定义文件失败。 BAM 跟踪文件采用二进制文件格式，因此不能进行编辑，而只能重新生成。 如果需要 BAM 跟踪文件，则可能需要执行以下任一操作：<br /><br /> -避免经常在生成过程中更新版本号<br />-延迟生成跟踪配置文件，直到版本号是稳定的 BAM|  
|通过使用 Web Services 发布向导发布的 Web Services|当使用 Web 服务发布向导时生成 ASP.NET Web 接口时，BizTalk Server 程序集的程序集版本包含在 ASP.NET 的源代码。 程序集版本号在由 ASP.NET 接口的运行时使用的 Web 服务操作的 bodyTypeAssemblyQualifiedName 属性的一部分。 如果 BizTalk Server 程序集的版本号而无需更新 bodyTypeAssemblyQualifiedName 属性发生更改，然后将 BizTalk server 拒绝后续的 Web 服务操作。<br /><br /> 如果接收位置使用 XmlDefaultPipeline，则订阅依赖于文档类型。 订阅使用嵌入的程序集信息，并会在程序集不存在时失败。 如果使用 PassThruPipeline（公开某一端口并让向导创建接收位置时的默认值），则订阅会忽略此嵌入的程序集信息。|