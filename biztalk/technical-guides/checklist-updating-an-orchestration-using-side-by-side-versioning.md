---
title: 清单： 更新业务流程使用的并行版本控制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97f66987-0269-4dfe-a648-7b68412e86fe
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8e9ed9f260b7b7b8b269e6a4b5e22411ce05b5c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009934"
---
# <a name="checklist-updating-an-orchestration-using-side-by-side-versioning"></a>清单： 更新业务流程使用的并行版本控制
对业务流程更改可以将更多地涉及不是更改为其他项目，比如地图。 如果你有生存期较短的业务流程，简单的更新可能足够。 但是，如果你有长时间运行业务流程，或者无法终止现有实例，则的并行版本控制将唯一的选项。  
  
 当业务流程处理长时间运行事务时，你无法立即更改业务流程的已更新版本。 你必须允许要完成处理其消息，以便它们不会丢失的原始版本。 为此，请将已更新的业务流程与原始版本部署到同一应用程序。 然后，停止原始版本并启动已更新的版本，以便在先前版本继续处理任何正在处理的消息时可以接收所有新消息。 在原始业务流程完成其所有消息的处理后，从其部署的 BizTalk 应用程序中取消对它的部署。  
  
|步骤|参考|  
|-----------|---------------|  
|对业务流程进行必要的更改后, 递增程序集版本号。|[如何更新程序集](../technical-guides/how-to-update-an-assembly.md)|  
|部署到 BizTalk 应用程序，从 Visual Studio 程序集，然后测试程序集。 **注意：** 确保你选择要将程序集安装在 GAC 中的部署选项。|[部署到 BizTalk 应用程序程序集从 Visual Studio BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719)。|  
|从测试环境到.msi 文件中的应用程序导出程序集。|[如何将应用程序导出到 .msi 文件](../technical-guides/how-to-export-an-application-to-an-msi-file.md)|  
|.Msi 文件导入生产环境中包含你想要更新的业务流程的 BizTalk 应用程序。 **注意：** 可以为测试程序集，以及将其部署到生产环境中使用以下步骤。|[如何从 .msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)|  
|绑定更新业务流程作为原始业务流程中使用相同的绑定。|[如何配置适用于业务流程的绑定](http://go.microsoft.com/fwlink/?LinkId=154850)(http://go.microsoft.com/fwlink/?LinkId=154850)。|  
|取消登记原始业务流程，然后启动已更新的业务流程。 **注意：** 以避免任何已删除的消息，你应执行此操作以编程方式。|有关以编程方式部署业务流程的详细信息，请参阅[部署和启动新版本的业务流程以编程方式](http://go.microsoft.com/fwlink/?LinkId=154851)(http://go.microsoft.com/fwlink/?LinkId=154851)。<br /><br /> 有关手动部署业务流程的详细信息，请参阅以下 BizTalk Server 帮助中：<br /><br /> -   [如何取消登记业务流程](http://go.microsoft.com/fwlink/?LinkId=154852)(http://go.microsoft.com/fwlink/?LinkId=154852)。<br />-   [如何登记业务流程](http://go.microsoft.com/fwlink/?LinkId=154853)(http://go.microsoft.com/fwlink/?LinkId=154853)。<br />-   [如何启动 Orchestration](http://go.microsoft.com/fwlink/?LinkId=154854) (http://go.microsoft.com/fwlink/?LinkId=154854)。|  
|监视的系统的使用组中心数据库的原始 orchestration 版本实例页上的查询视图。|[如何查看为业务流程的实例信息](http://go.microsoft.com/fwlink/?LinkId=154855)(http://go.microsoft.com/fwlink/?LinkId=154855)。|  
|完成所有活动、 已冻结，和挂起实例后，取消部署应用程序从原始的业务流程。|[如何从应用程序删除业务流程](http://go.microsoft.com/fwlink/?LinkId=154856)(http://go.microsoft.com/fwlink/?LinkId=154856)。|  
|（可选） 从运行应用程序的每台计算机上的 GAC 中卸载原始程序集版本。|[如何从 GAC 中卸载程序集](http://go.microsoft.com/fwlink/?LinkId=154857)(http://go.microsoft.com/fwlink/?LinkId=154857)。|  
  
## <a name="binding-to-receive-ports-and-locations"></a>绑定，使其接收端口和位置  
 如果你想要创建新接收端口和业务流程的新版本的位置，只需将绑定到的新端口和登记/启动新的项目通常会足够。 创建新的接收位置和端口通常是首选的方法，尤其是如果你的方案使用长时间运行业务流程的关联数仍收到需要处理。 在这种情况下，你可能无法重用现有的接收端口或执行征用。 如果创建新端口，请确保有可能你的后端和合作伙伴系统以处理此更改。 如果没有，你将必须等待所有的长时间运行实例，以在升级之前并且最后结束。  
  
 如果你想要使用现有的端口，请执行以下操作：  
  
1.  绑定到现有端口业务流程的新版本。  
  
2.  取消登记 （但不是会停止） 旧版本的业务流程。  
  
3.  登记和启动新的业务流程版本。  
  
    > [!NOTE]  
    >  可以使用脚本若要执行步骤 2 和 3 中一个事务，以便消息将不缺少之间手动单击订阅。