---
title: 如何升级业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96d3b340d796d2cf3a63e206a74b0faa43acafa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333644"
---
# <a name="how-to-upgrade-an-orchestration"></a>如何升级业务流程
如何更新业务流程处理长期事务或正在等待来自要求-响应端口的响应时，生产环境中运行的业务流程。

## <a name="overview"></a>概述
 当业务流程不处理长时间运行的事务时，您可以更新它中所述[核对清单：更新 BizTalk 应用程序中的项目](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)。 当业务流程处理长期事务时，但是，您不能转换到更新版本的业务流程立即。 必须允许原始版本完成处理其消息，以便不会丢失。 若要实现此目的，你部署到与原始版本相同的应用程序已更新的业务流程。 然后，停止原始版本并启动的更新的版本，以使其接收所有新消息，而以前的版本将继续处理任何未送达消息。 原始业务流程完成其所有消息的处理后，取消对它在其中部署的 BizTalk 应用程序。  
  
 有关此方案的详细信息，请参阅[方案：更新应用程序项目](../core/scenario-updating-application-artifacts.md)。  
  
> [!IMPORTANT]
>  如果多个业务流程绑定到同一接收端口，并启动或登记每个业务流程时，将到系统引入重复的消息。  
  
> [!NOTE]
>  升级到新的业务流程时，某些业务流程实例也会挂起 （可恢复） 在高负载下由于旧的业务流程和新的业务流程升级期间之间的争用条件。 若要手动恢复这些业务流程实例，请参阅[如何恢复挂起的业务流程实例](../core/how-to-resume-suspended-orchestration-instances.md)。

## <a name="prerequisites"></a>先决条件  
是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 你的帐户还必须具有本地文件系统和全局程序集缓存的读/写权限。 在本地计算机上的管理员帐户拥有此权限。  

详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。 
 
## <a name="update-an-orchestration"></a>更新业务流程  
  
1.  向业务流程进行必要的更改。  
  
2.  递增程序集的版本号，如下所示：  
  
    1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**以启动项目的项目设计器。  
  
    2.  单击**应用程序**选项卡上，如果尚未处于活动状态，然后依次**程序集信息**。  
  
    3.  在右窗格中，增加程序集的版本号。 应增加仅主要或次要版本数。 主版本号是序列中的第一个数字 (**0**.0.0.0); 次版本号是序列中的第二个数字 (0。**0**.0.0)。 BizTalk Server 将无法识别版本号的更改是在序列中，例如 0.0 更高版本。**0**.0 或 0.0.0。**0**。  
  
    4.  单击**确定**以关闭**程序集信息**对话框。  
  
    5.  保存项目。  
  
3.  部署到 BizTalk 应用程序的程序集从 Visual Studio。 有关说明，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 请确保选择要将程序集安装到 GAC 中的部署选项。  
  
4.  测试包含业务流程的程序集。  
  
5.  将程序集导出到.msi 文件，在测试环境中应用程序中，如中所述[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
    > [!NOTE]
    >  您可以使用以下步骤来测试该程序集，以及将其部署到生产环境。 有关开发、 测试、 过渡和生产环境中的应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。  
  
6.  将.msi 文件导入包含你想要更新，如中所述的业务流程在生产环境中的 BizTalk 应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
7.  绑定更新业务流程与原始业务流程，使用相同的绑定，如中所述[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
8.  取消登记原始业务流程，并启动已更新业务流程。 若要避免删除任何消息，你应执行此操作以编程方式，如中所述[部署和启动新版本的业务流程以编程方式](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)。 或者，可以执行这些步骤中所述手动[如何取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)，[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)，和[如何启动业务流程](../core/how-to-start-an-orchestration.md).  
  
9. 监视的系统实例的原始业务流程版本使用组中心页查询视图，如中所述[如何查看业务流程的实例信息](../core/how-to-view-instance-information-for-an-orchestration.md)。  
  
10. 完成所有活动的、 已冻结的和已挂起实例后，取消部署原始业务流程应用程序，如中所述[如何从应用程序中删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)。  
  
11. （可选） 从运行该应用程序，每台计算机上的 GAC 卸载原始程序集版本，如中所述[如何从 GAC 卸载程序集](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)。  
  
## <a name="see-also"></a>请参阅  
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)   
 [管理业务流程](../core/managing-orchestrations.md)