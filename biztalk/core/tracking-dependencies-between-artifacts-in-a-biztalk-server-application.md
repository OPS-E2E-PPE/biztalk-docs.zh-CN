---
title: 跟踪在 BizTalk Server 应用程序中的项目之间依赖项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 503cadfc-08e5-4b34-94a2-3b0ea6ad6228
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3edd162075f1ad660c005fd387ac9bc6c8c79e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279949"
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>跟踪 BizTalk Server 应用程序中的项目之间的依存关系
典型的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序包括各种项目，如业务流程、发送端口、接收位置、管道、架构、映射等。 所有这些项目均相互依存。 下表列出了这些依存关系：  
  
|项目|业务流程|发送端口|接收端口|接收位置|管道|地图|架构|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**业务流程**||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**发送端口**|![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**接收端口**|![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**接收位置**|||![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**管道**||![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**地图**||![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**架构**||||||![使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 如此表所示，有两种依存关系模式。  
  
-   使用 (![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")) – 项目使用了另一个项目，例如，发送端口将使用管道。  
  
-   使用者 (![由](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")) – 项目由另一个项目，例如，发送端口由业务流程。  
  
 鉴于这些依存关系，如果需要更新某个项目，你必须了解依存关系层次结构中哪些项目需要停止或重新部署。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中提供了此类依存关系信息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台以两种模式 – 显示依赖项信息，是否项目使用了另一个项目*以及*项目是否由另一个项目。  
  
## <a name="viewing-dependencies"></a>查看依存关系  
 本部分提供了有关如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台查看依存关系的信息。  
  
> [!NOTE]
>  以下过程提供了有关如何查看某个业务流程的依存关系的说明。 你也可以按照同样的说明查看其他项目的依存关系。  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>查看某个项目的依存关系的步骤  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开应用程序，，然后单击**业务流程**。 在中间窗格中，右键单击你想要查看这些依赖项，，然后单击业务的流程**查看依赖关系**。  
  
2.  底部窗格中，**依赖项统计信息**窗格中，显示两种类别的依赖关系。 **使用者**类别显示使用该特定的业务流程的项目。 **使用**类别显示由特定的业务流程的项目。  
  
     ![为业务流程的依赖关系](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
     因为没有其他项目是依赖于业务流程，**使用者**业务流程的依赖项类别为空。 但是，在**使用**依赖项模式下图显示是否依赖于一个发送端口业务流程。 依存关系的数量显示为超链接，如果单击此超链接，将仅显示该业务流程所依赖的发送端口。 请注意，即使在你单击该超链接以列出发送端口之后，依存关系窗格仍然会显示该业务流程的依存统计，而不是发送端口的依存统计。  
  
     你可以右键单击发送端口，然后单击**查看依赖关系**同样，若要查看发送端口的依赖关系矩阵。 你可以向上查看任何级别的此类依存关系树。 你在依存关系树中所处的级别将在该窗格顶部通过一串面包屑来显示，如下图所示。  
  
     ![Bread 依赖关系树的导航](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")