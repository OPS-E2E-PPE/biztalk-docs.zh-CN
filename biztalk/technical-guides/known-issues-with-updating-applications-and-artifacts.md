---
title: 已知问题，并将更新应用程序和项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 220ea03c-d453-40cc-8ddb-18a96f8ddfe5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5c322006393b0571b64eaace05a67626f31fb58
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401226"
---
# <a name="known-issues-with-updating-applications-and-artifacts"></a>更新的应用程序和项目的已知的问题
## <a name="updating-an-application"></a>更新应用程序  
 **移除或删除项目不会删除它从所有位置**  
  
 移除或删除项目将其从删除 BizTalk Server 数据库，以便它不会再出现在管理控制台或 BTSTask ListApp 命令生成的应用程序的项目列表中。 如果它存在于这些位置中，它不会从 Windows 注册表、 全局程序集缓存 (GAC)、 虚拟目录或文件系统中，删除该项目。 在发送端口的情况下发送端口组、 接收端口，以及完全接收位置，只存在于 BizTalk 管理数据库，此操作删除该项目。  
  
## <a name="updating-an-artifact"></a>更新某一项目  
 **删除或更改项目的状态可能会导致应用程序无法正常工作**  
  
 如果您添加从应用程序的不同而不同的引用，对项目在其依赖于另一个应用程序，或删除该项目的状态进行任何更改具有依存关系的应用程序将无法正常工作。 有关更改项目的状态的详细信息，请参阅部分中针对相应项目中[管理项目](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。  
  
 **不支持.NET 策略文件**  
  
 在 BizTalk Server 中不支持使用.NET 策略文件。 这是因为策略文件可能无法按预期方式工作。 策略文件将.NET 重定向到指定的程序集版本在 gac 中，但[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通常从缓存或 BizTalk 管理数据库访问程序集和项目数据。 具体取决于项目类型、 缓存情况，是否重新启动主机实例，该策略文件可能是否正确的结果。  
  
## <a name="updating-an-assembly"></a>更新的程序集  
 **对程序集的更改可能会生效，如果主机未停止**  
  
 BizTalk 程序集必须遵循.NET 版本控制规则。 其主要含义是，一次生成的其他.NET 项目或程序集 （包括 BizTalk 项目） 的特定版本的 BizTalk 项目，将继续使用该版本，直到它已针对较新版本重新生成。  
  
 在 BizTalk 项目上的版本号不会更改，而不必停止和启动加载类型的 BizTalk 主机实例重新部署程序集时，与.NET 版本控制相关的开发过程中会出现一个常见问题。  
  
 再次运行该过程时，更改不会生效。 这是因为.NET 程序集加载到内存的方式。 因为主机已经具有该程序集的内存中副本，它不会重新加载该程序集时的新副本将放入全局程序集缓存 (GAC)。 例如，如果在部署与业务流程的程序集的版本 1.0.0.0 和对业务流程进行运行，并更改，但不是更改版本号，所做的更改不执行操作才会生效。 停止主机实例后，发布的程序集的内存中副本，该主机实例启动时再次它重新加载该程序集的新副本并获取所做的更改。 如果部署新版本，例如版本 2.0.0.0，并加载，则所做的更改将生效。  
  
 **更改程序集版本可能会中断程序集和引用它的版本的项之间的关系**  
  
 在.NET Framework 开发是典型的程序集版本号更新到当前的内部版本号，进行生成时。 但是，当开发 BizTalk 解决方案，则更改程序集的版本号可能会中断程序集和引用其程序集版本号的 DLL 的依赖项之间的关系。 下表列出了通过使用其版本号和更改程序集版本号的效果，请参阅 BizTalk Server 程序集的项。  
  
|实体|更改程序集版本号的效果|  
|------------|------------------------------------------------|  
|绑定文件|更改程序集版本会导致引用程序集失败的任何现有绑定文件。 这是因为绑定文件的属性，包括其版本号引用程序集。<br /><br /> 可以使用记事本或其他编辑器更新绑定文件中的版本信息。 可以重新部署该解决方案，并使用 BizTalk Server 管理控制台，然后重新生成绑定文件。 最后，可以使用脚本自动执行部署和版本控制。 有关部署的详细信息，请参阅[部署和管理 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154210)(http://go.microsoft.com/fwlink/?LinkID=154210)。|  
|BAM 跟踪配置文件定义 (.btt) 文件|更改程序集版本会导致任何现有 BAM 跟踪配置文件定义文件失败。 BAM 跟踪文件为二进制文件格式的因此它们不能进行编辑，而是必须重新生成。 如果需要 BAM 跟踪配置文件，则可能需要执行以下任一操作：<br /><br /> -避免在生成过程中经常更新版本号<br />-延迟生成 BAM 跟踪配置文件，等到版本号稳定|  
|通过使用 Web Services 发布向导发布的 web 服务|当 Web Services 发布向导用于生成 ASP.NET Web 接口时，ASP.NET 源代码中包含的 BizTalk Server 程序集的程序集版本。 在运行时由 ASP.NET 接口使用程序集的版本号作为 Web 服务操作的 bodyTypeAssemblyQualifiedName 属性的一部分。 如果 BizTalk Server 程序集的版本号而不更新 bodyTypeAssemblyQualifiedName 属性发生更改，然后将 BizTalk server 拒绝后续的 Web 服务操作。<br /><br /> 如果接收位置使用 XmlDefaultPipeline，则订阅依赖于文档类型。 它使用嵌入的程序集信息，如果该程序集不存在，则将失败。 如果使用 PassThruPipeline (公开某一端口并让向导创建接收位置的情况下时的默认值），则订阅会忽略此嵌入的程序集信息。|