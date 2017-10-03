---
title: "如何升级业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd9fa8e98b62ec92b1313cc1028efc5320ce17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-upgrade-an-orchestration"></a>如何升级业务流程
如何更新业务流程处理长时间运行的事务或正在等待从请求-响应端口的响应时，生产环境中运行的业务流程。

## <a name="overview"></a>概述
 在业务流程不处理长时间运行事务时，你可以更新它中所述[清单： 更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。 但是当某业务流程处理长期事务时，您不能立即转换到该业务流程的已更新版本。 必须允许原始版本完成其消息的处理，这样才不会丢失消息。 为此，请将已更新的业务流程与原始版本部署到同一应用程序。 然后，停止原始版本并启动已更新的版本，以便在先前版本继续处理任何正在处理的消息时可以接收所有新消息。 在原始业务流程完成其所有消息的处理后，从其部署的 BizTalk 应用程序中取消对它的部署。  
  
 有关此方案的详细信息，请参阅[方案： 更新应用程序项目](../core/scenario-updating-application-artifacts.md)。  
  
> [!IMPORTANT]
>  如果多个业务流程绑定到同一接收端口，并且每个业务流程都已启动或登记，则会向系统引入重复的消息。  
  
> [!NOTE]
>  在升级到新的业务流程时，由于升级期间旧业务流程和新业务流程之间的争用情况，在任务繁忙时某些业务流程实例可能会成为“已挂起（可恢复）”。 若要手动恢复这些业务流程实例，请参阅[如何恢复挂起的业务流程实例](../core/how-to-resume-suspended-orchestration-instances.md)。

## <a name="prerequisites"></a>先决条件  
使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 你的帐户还必须在本地文件系统和全局程序集缓存上的读/写权限。 本地计算机的管理员帐户拥有此权限。  

有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。 
 
## <a name="update-an-orchestration"></a>更新业务流程  
  
1.  对业务流程进行必要的更改。  
  
2.  递增程序集的版本号，如下所示：  
  
    1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**以启动项目设计器中为该项目。  
  
    2.  单击**应用程序**选项卡上，如果尚未处于活动状态，并依次**程序集信息**。  
  
    3.  在右窗格中，递增程序集的版本号。 应该只递增主版本号或次版本号。 主版本号是序列中的第一个数字 (**0**.0.0.0); 的次版本号是序列中的第二个数字 (0。**0**.0.0)。 BizTalk Server 将无法识别序列，如 0.0 中更高版本的版本编号更改。**0**.0 或 0.0.0。**0**。  
  
    4.  单击**确定**关闭**程序集信息**对话框。  
  
    5.  保存项目。  
  
3.  将程序集从 Visual Studio 部署到 BizTalk 应用程序。 有关说明，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 确保选择部署选项以在 GAC 中安装程序集。  
  
4.  测试包含业务流程的程序集。  
  
5.  将程序集导出到.msi 文件，测试环境中的应用程序从中, 所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
    > [!NOTE]
    >  您可以使用以下步骤测试程序集并将程序集部署到您的生产环境中。 有关在开发、 测试、 过渡和生产应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。  
  
6.  导入生产环境中包含你想要更新中, 所述的业务流程的 BizTalk 应用程序的.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
7.  绑定更新业务流程作为原始业务流程，使用相同的绑定中所述[如何将绑定配置为业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
8.  取消登记原始业务流程，然后启动已更新的业务流程。 若要避免任何已删除的消息，你应执行此操作以编程方式中, 所述[部署和启动新版本的业务流程以编程方式](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)。 或者，可以执行这些步骤中所述手动[如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)，[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)，和[如何启动 Orchestration](../core/how-to-start-an-orchestration.md).  
  
9. 监视的系统中所述，使用组中心数据库的原始 orchestration 版本的实例页上查询视图[如何查看实例信息为业务流程](../core/how-to-view-instance-information-for-an-orchestration.md)。  
  
10. 完成所有活动、 已冻结，和挂起实例后，取消部署该应用程序，从原始的业务流程中所述[如何从应用程序删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)。  
  
11. 根据需要从运行该应用程序，每台计算机上的 GAC 卸载原始程序集版本中所述[如何从 GAC 中卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
## <a name="see-also"></a>另请参阅  
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)   
 [管理业务流程](../core/managing-orchestrations.md)