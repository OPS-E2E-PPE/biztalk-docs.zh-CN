---
title: 实现版本控制策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a3c7af6-6277-4667-8f14-e6d1cb9e99d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8990fb3d65b29609738ed398829a438478eeabb3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015038"
---
# <a name="implementing-a-versioning-strategy"></a>实现版本控制策略
版本控制是项目的更新实现和递增其版本号的操作。  
  
## <a name="general-versioning-issues"></a>常规版本控制问题  
 BizTalk 应用程序版本控制可以成为一个问题，当你需要运行两个版本的 BizTalk 解决方案的并排方案，或如果您不能计划要部署的新版本的 BizTalk 应用程序停机时间。 如果不需要运行两个版本的同时 （例如，如果不有任何长时间运行的业务流程） 解决方案，它是完全可以接受要取消部署旧版本并将其部署新版本作为版本控制策略 （无程序集版本控制）。 这是一种可能的版本控制策略，但我们仍建议使用 （若要让您知道哪些版本的 BizTalk 服务器上部署） 的文件版本号递增。 有关更新部署的应用程序的详细信息，请参阅[清单： 更新的程序集](../technical-guides/checklist-updating-an-assembly.md)。  
  
 如果你需要支持长时间运行的业务流程，和/或需要执行任何 BizTalk 应用程序停机的情况下的 BizTalk 应用程序部署，然后可靠的 BizTalk 版本控制策略需要实现和实施用于不同的端到端版本控制方案。 这包括.NET 程序集版本控制和版本控制的所有 BizTalk 项目。 这包括架构、 映射、 管道、 管道组件、 业务流程、 自定义适配器、 自定义类中调用的业务流程和映射、 业务规则和 BAM。 有关通过并行版本控制的详细信息，请参阅[更新使用的并行版本控制](../technical-guides/updating-using-side-by-side-versioning.md)。  
  
## <a name="versioning-an-assembly"></a>程序集版本控制  
 更新程序集时，您可以在以下选择：  
  
- 选择固定的程序集版本为给定可交付结果和的文件版本号递增。  
  
- 开发过程中递增程序集版本和文件版本。  
  
  下表比较了这些方法：  
  
|**固定的程序集版本，动态文件版本**|**动态程序集版本，固定或动态文件版本**|  
|------------------------------------------------------|-----------------------------------------------------------------|  
|程序集版本号 = 固定版本号<br /><br /> 文件版本号 = 内部版本号|程序集版本号 = 内部版本号<br /><br /> 文件版本号 = 内部版本号|  
|BizTalk Server 运行时可能会选取错误的程序集的版本，如果安装多个程序集。|BizTalk Server 始终运行最新版本的程序集，即使安装了多个程序集。|  
|在任何时候只能部署解决方案的一个版本。|（尽管该解决方案，如架构定义的其他方面可能会发生冲突），可以并列部署解决方案的不同版本。|  
|需要重新启动 BizTalk 主机以强制加载已更新的程序集。|强制加载新程序集的 BizTalk Server。|  
|由于无需编辑引用程序集版本号的文件（例如绑定文件和跟踪配置文件），因此进行新部署的工作量较轻。|由于需要不断地使用新版本来更新引用程序集版本号的文件，因此部署的工作量较重。|  
  
 您可以选择使用固定的程序集版本和动态文件版本方法，如果您是在设计系统原型或开发任何其他类型的项目不会释放。 如果不打算将应用程序交付给最终用户，则可以通过固定程序集版本和以增量形式更改文件版本号的方法来简化部署并减少中断的依存关系。 对于版本跟踪，必须记住为每个内部版本以增量形式更改文件版本号。  
  
 如果要生成交付给最终用户的项目，则应考虑以增量方式更改程序集版本号，也可以存储一个有意义的文件版本号。 虽然此方法需要进行更多的工作来修改内部版本号和相关联的依存关系，但它可以确保使用最新的程序集。 通过使用自动部署脚本，可以减少版本控制的影响。 若要查看部署示例，请参阅[应用程序部署 （BizTalk Server 示例文件夹）](http://go.microsoft.com/fwlink/?LinkId=155134) (<http://go.microsoft.com/fwlink/?LinkId=155134>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
> [!NOTE]  
>  应选择的版本控制机制，它可确保适当的文件被传递，并且，简化了维护和增强功能。  
  
 有关版本控制问题的详细信息，请参阅[BizTalk Server 项目版本控制](http://go.microsoft.com/fwlink/?LinkID=154209)(<http://go.microsoft.com/fwlink/?LinkID=154209>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。