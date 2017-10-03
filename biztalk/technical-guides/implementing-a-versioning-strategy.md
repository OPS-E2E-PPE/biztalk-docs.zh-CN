---
title: "实现版本控制策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a3c7af6-6277-4667-8f14-e6d1cb9e99d4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bab9863107b26df615af1b51398ca4c314ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-a-versioning-strategy"></a>实现版本控制策略
版本控制是项目的更新的实现以及其版本号递增的操作。  
  
## <a name="general-versioning-issues"></a>一般版本控制问题  
 BizTalk 应用程序版本控制可以成为一个问题，当您需要同时运行两个版本的 BizTalk 解决方案由并行，或者如果您无法计划 BizTalk 应用程序停机时间从而部署的新版本。 如果不需要运行两个版本的同时 （例如，如果你不有任何长时间运行业务流程） 解决方案，它是完全可以接受取消部署的旧版本和版本控制策略 （没有程序集版本控制） 作为部署的新版本。 这是可能的版本控制策略，但我们仍建议使用 （若要让你知道哪个版本部署在 BizTalk server 上） 的文件版本号递增。 有关更新部署的应用程序的详细信息，请参阅[清单： 更新程序集](../technical-guides/checklist-updating-an-assembly.md)。  
  
 如果你需要支持长时间运行业务流程和/或你需要执行 BizTalk 应用程序部署，且无 BizTalk 应用程序停机时间，然后可靠的 BizTalk 版本控制策略需要进行实现，并且练习用于不同的端到端版本控制方案。 这包括.NET 程序集版本控制和版本控制的所有 BizTalk 项目。 这包括架构、 地图、 管道、 管道组件、 业务流程、 自定义适配器、 自定义类中被调用的业务流程和图、 业务规则和 BAM。 有关的并行版本控制的详细信息，请参阅[更新使用的并行版本控制](../technical-guides/updating-using-side-by-side-versioning.md)。  
  
## <a name="versioning-an-assembly"></a>程序集版本控制  
 在更新程序集时，你可以在以下选择：  
  
-   选择是固定的程序集的版本提供可交付结果和的文件版本号递增。  
  
-   在开发过程增加程序集版本和文件版本。  
  
 下表中，这些方法进行比较：  
  
|**固定的程序集版本，动态文件版本**|**动态程序集版本，固定或动态文件版本**|  
|------------------------------------------------------|-----------------------------------------------------------------|  
|程序集版本号 = 固定版本号<br /><br /> 文件版本号 = 内部版本号|程序集版本号 = 内部版本号<br /><br /> 文件版本号 = 内部版本号|  
|如果多个程序集安装 BizTalk Server 运行时可能会选择错误版本的程序集。|BizTalk Server 始终运行最新版本的程序集，即使安装多个程序集。|  
|在任何时候只能部署解决方案的一个版本。|（尽管解决方案，例如架构定义的其他方面，可能会发生冲突），可以并排部署的解决方案的不同版本。|  
|需要重新启动 BizTalk 主机以强制加载已更新的程序集。|强制 BizTalk Server，以加载新的程序集。|  
|由于无需编辑引用程序集版本号的文件（例如绑定文件和跟踪配置文件），因此进行新部署的工作量较轻。|由于需要不断地使用新版本来更新引用程序集版本号的文件，因此部署的工作量较重。|  
  
 你可以选择使用的固定的程序集版本和动态文件版本方法，如果你是原型制作系统或开发任何其他类型的项目不会释放。 如果不打算将应用程序交付给最终用户，则可以通过固定程序集版本和以增量形式更改文件版本号的方法来简化部署并减少中断的依存关系。 对于版本跟踪，必须记住为每个内部版本以增量形式更改文件版本号。  
  
 如果要生成交付给最终用户的项目，则应考虑以增量方式更改程序集版本号，也可以存储一个有意义的文件版本号。 虽然此方法需要进行更多的工作来修改内部版本号和相关联的依存关系，但它可以确保使用最新的程序集。 通过使用自动部署脚本，可以减少版本控制的影响。 若要查看部署示例，请参阅[应用程序部署 （BizTalk Server 示例文件夹中）](http://go.microsoft.com/fwlink/?LinkId=155134) (http://go.microsoft.com/fwlink/?LinkId=155134) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
> [!NOTE]  
>  你应选择的版本控制机制，它可确保正确文件被传递，并且它可用于简化维护和增强功能。  
  
 有关版本控制问题的详细信息，请参阅[BizTalk 服务器项目版本控制](http://go.microsoft.com/fwlink/?LinkID=154209)(http://go.microsoft.com/fwlink/?LinkID=154209) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。