---
title: 清单：正在更新业务流程使用的并行版本控制 |Microsoft Docs
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
ms.openlocfilehash: bd8c0f9e1424982324aff88115188b9d6a74f835
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397088"
---
# <a name="checklist-updating-an-orchestration-using-side-by-side-versioning"></a>清单：正在更新业务流程使用的并行版本控制
可以不是将更改为其他项目，如映射更多地涉及到业务流程的更改。 如果你有生存期较短的业务流程，简单的更新可能是足够。 但如果您有长时间运行的业务流程，或者不能终止现有实例，然后通过并行版本控制将您的唯一选择。  
  
 如果业务流程处理长期事务，则无法立即更改该业务流程的已更新版本。 必须允许原始版本完成处理其消息，以便它们不会丢失。 若要实现此目的，你部署到与原始版本相同的应用程序已更新的业务流程。 然后，停止原始版本并启动的更新的版本，以使其接收所有新消息，而以前的版本将继续处理任何未送达消息。 原始业务流程完成其所有消息的处理后，取消对它在其中部署的 BizTalk 应用程序。  
  
|步骤|参考|  
|-----------|---------------|  
|后向业务流程进行必要的更改，递增程序集的版本号。|[如何更新程序集](../technical-guides/how-to-update-an-assembly.md)|  
|部署到 BizTalk 应用程序，该程序集从 Visual Studio，然后测试程序集。 **注意：** 请确保选择要将程序集安装到 GAC 中的部署选项。|[部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。|  
|将程序集导出到.msi 文件在测试环境中应用程序中。|[如何将应用程序导出到 .msi 文件](../technical-guides/how-to-export-an-application-to-an-msi-file.md)|  
|将.msi 文件导入包含你想要更新的业务流程在生产环境中的 BizTalk 应用程序。 **注意：** 您可以使用以下步骤来测试该程序集，以及将其部署到生产环境。|[如何从 .msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)|  
|绑定更新业务流程与原始业务流程中使用相同的绑定。|[如何配置业务流程绑定](http://go.microsoft.com/fwlink/?LinkId=154850)(http://go.microsoft.com/fwlink/?LinkId=154850)。|  
|取消登记原始业务流程，并启动已更新业务流程。 **注意：** 若要避免删除任何消息，你应执行此操作以编程方式。|有关以编程方式部署该业务流程的详细信息，请参阅[部署和启动新版本的业务流程以编程方式](http://go.microsoft.com/fwlink/?LinkId=154851)(http://go.microsoft.com/fwlink/?LinkId=154851)。<br /><br /> 手动部署该业务流程的详细信息，请参阅 BizTalk Server 帮助中的以下：<br /><br /> -   [如何取消登记业务流程](http://go.microsoft.com/fwlink/?LinkId=154852)(http://go.microsoft.com/fwlink/?LinkId=154852)。<br />-   [如何登记业务流程](http://go.microsoft.com/fwlink/?LinkId=154853)(http://go.microsoft.com/fwlink/?LinkId=154853)。<br />-   [如何启动业务流程](http://go.microsoft.com/fwlink/?LinkId=154854)(http://go.microsoft.com/fwlink/?LinkId=154854)。|  
|监视的系统实例的原始业务流程版本使用组中心页查询视图。|[如何查看业务流程的实例信息](http://go.microsoft.com/fwlink/?LinkId=154855)(http://go.microsoft.com/fwlink/?LinkId=154855)。|  
|完成所有活动的、 已冻结的和已挂起实例后，取消部署原始业务流程从应用程序。|[如何从应用程序中删除业务流程](http://go.microsoft.com/fwlink/?LinkId=154856)(http://go.microsoft.com/fwlink/?LinkId=154856)。|  
|（可选） 从运行该应用程序的每台计算机上的 GAC 卸载原始程序集版本。|[如何从 GAC 卸载程序集](http://go.microsoft.com/fwlink/?LinkId=154857)(http://go.microsoft.com/fwlink/?LinkId=154857)。|  
  
## <a name="binding-to-receive-ports-and-locations"></a>若要接收端口和位置的绑定  
 如果你想要创建新的接收端口和业务流程的新版本的位置，只需绑定到的新端口和登记/启动新项目通常是足够。 创建新的接收位置和端口通常是首选的方法，尤其是如果你的方案使用长时间运行的业务流程关联的数量仍收到需要进行处理。 在这种情况下，您可能不能重复使用现有的接收端口或执行征用。 如果您创建新的端口，请确保很可能您的后端和合作伙伴系统来处理此更改。 如果没有，你将需要等待所有长时间运行实例，若要在升级之前作为结束。  
  
 如果你想要使用现有端口，请执行以下操作：  
  
1.  将新版本的业务流程绑定到现有的端口。  
  
2.  取消登记 （但不是会停止） 的旧的业务流程版本。  
  
3.  登记并启动新的业务流程版本。  
  
    > [!NOTE]  
    >  可以使用脚本执行步骤 2 和 3 在一个事务，使消息不会丢失之间手动单击的订阅。