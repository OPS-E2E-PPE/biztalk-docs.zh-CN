---
title: "如何部署与现有版本运行的并行应用程序的新版本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1677c6a5-2c4c-4d70-ab83-f7e0bb3aaf6e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053145729546453b959dc35c7901932c1c8690c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a>如何将应用程序的新版本部署为与现有版本并行运行
如何部署的应用程序将运行并排显示的新版本与现有版本。 

## <a name="overview"></a>概述
您可能要在以增量方式实施主要应用程序升级时（例如，最初只是使它可用于一部分的业务合作伙伴，而不是一下子就可用于所有合作伙伴），执行此类部署。 通过使用此方法，您可以继续运行现有应用程序，以便为尚未使用新版本的用户提供服务，直到您已准备就绪，可以完全转换到新版本。 在这种情况下的背景信息，请参阅[方案： 部署两个版本的应用程序](../core/scenario-deploying-two-versions-of-an-application.md)。  
  
 您创建应用程序版本的方式与创建程序集版本（通过递增版本号）的方式不同。 与之相反，您创建与原始应用程序具有不同名称的新应用程序，并且用应用程序项目的新版本填充它。  
  
 因为许多类型的项目（例如程序集）只能存在于 BizTalk 组的一个应用程序中，所以，您必须首先递增已在该组中存在的所有程序集的版本号，然后才能将它们部署到新的应用程序中。 有关详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  

## <a name="prerequisites"></a>先决条件  
使用是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 你的帐户还必须在本地文件系统和全局程序集缓存上的读/写权限。 本地计算机的管理员帐户拥有此权限。  

有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。 
  
## <a name="deploy-a-new-version-of-an-application"></a>部署应用程序的新版本  
  
1.  在 Visual Studio 中，对您要部署到应用程序的新版本中的程序集进行必需的更改。  
  
2.  按如下所示，递增每个程序集的版本号：  
  
    1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**以启动项目的项目设计器。  
  
    2.  单击**应用程序**如果处于非活动状态，选项卡，然后单击**程序集信息**按钮。  
  
    3.  增加程序集版本号，并依次**确定**。  
  
    4.  保存项目。  
  
    > [!NOTE]
    >  使用管道设计器对象模型以避免架构冲突时递增程序集版本。  
  
3.  在解决方案的每个项目的部署属性中，执行以下操作：  
  
    -   将应用程序名称更改为您要用于新应用程序的名称。  
  
    -   确保选择用于在全局程序集缓存 (GAC) 中安装这些程序集的选项。  
  
     有关说明，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 在您部署该解决方案时，这些程序集将部署到新应用程序中并安装在 GAC 中。  
  
4.  部署包含程序集的解决方案。 有关说明，请参阅[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
5.  创建新的接收端口和所需的任何接收位置，指定您希望合作伙伴将消息发送到的新 URL。 有关说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。 另请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
6.  如有必要，创建相应的发送端口中所述[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
7.  绑定到新创建新的应用程序接收和发送端口中, 所述[如何配置应用程序](../core/how-to-configure-an-application.md)。  
  
8.  从测试环境中，导出应用程序置于.msi 文件中所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
    > [!NOTE]
    >  您可以使用以下步骤测试应用程序以及将应用程序部署到您的生产环境中。 有关在开发、 测试、 过渡和生产应用程序部署任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。  
  
9. 将应用程序.msi 文件导入到生产环境中的 BizTalk 组中所述[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 如果应用程序需要引用，你可以添加它们时使用导入 MSI 向导，或更高版本中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
10. 将运行它时，每个主机实例上安装新的应用程序中所述[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。 请确认每个更新的程序集都已安装在作为该程序集宿主的各计算机上的 GAC 中。 如有必要，安装程序集在 GAC 中中, 所述[如何将程序集安装在 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)。  
  
11. 执行完整启动应用程序中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
12. 向您的合作伙伴发出通知，指示他们应开始将消息发送到新的 URLS。 在他们发送后，应用程序将开始为指定合作伙伴处理消息。  
  
## <a name="see-also"></a>另请参阅  
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)