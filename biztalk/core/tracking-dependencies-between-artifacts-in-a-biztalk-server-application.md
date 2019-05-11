---
title: 跟踪 BizTalk Server 应用程序中的项目之间的依赖项 |Microsoft Docs
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
ms.openlocfilehash: 1ba644a5a745b83c217d35b6697c2bf2c4444ca2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313812"
---
# <a name="tracking-dependencies-between-artifacts-in-a-biztalk-server-application"></a>跟踪 BizTalk Server 应用程序中的项目之间的依赖项
典型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序包括各种项目，如业务流程、 发送端口、 接收位置、 管道、 架构、 映射和点赞。 所有这些项目均相互依赖关系。 下表列出了这些依赖关系。  
  
|项目|业务流程|发送端口|接收端口|接收位置|管道|地图|架构|  
|---------------|-------------------|---------------|------------------|----------------------|--------------|----------|-------------|  
|**业务流程**||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||||  
|**发送端口**|![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**接收端口**|![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")||  
|**接收位置**|||![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|||  
|**管道**||![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||  
|**地图**||![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")|![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||||![使用](../core/media/dependency-using-icon.png "Dependency_Using_Icon")|  
|**架构**||||||![通过使用](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")||  
  
 如表所示，有两种模式的依赖项。  
  
- 使用 (![Using](../core/media/dependency-using-icon.png "Dependency_Using_Icon")) – 一个项目使用另一个项目，例如，发送端口将使用管道。  
  
- 使用者 (![由](../core/media/dependency-usedby-icon.png "Dependency_UsedBy_Icon")) – 一个项目使用被另一个项目，例如，发送端口使用业务流程。  
  
  在这些依赖关系，如果你需要更新某个项目，您必须知道哪些项目依赖项层次结构中的必须停止或重新部署。 此类依赖关系信息现已推出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示这两种模式 – 依赖关系信息是否项目使用另一个项目*以及*是否被另一个项目使用项目。  
  
## <a name="viewing-dependencies"></a>查看依赖项  
 本部分介绍如何查看依赖项使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
> [!NOTE]
>  以下过程提供了有关如何查看业务流程的依赖项的说明。 可以按照相同的说明查看其他项目的依赖关系。  
  
#### <a name="to-view-dependencies-for-an-artifact"></a>若要查看某一项目的依赖项  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开应用程序，然后单击**业务流程**。 在中间窗格中，右键单击你想要查看依赖关系，然后依次在业务的流程**查看依赖关系**。  
  
2. 在窗格底部**依存统计**窗格中，将显示两种类别的依赖项。 **使用者**类别显示使用该特定业务流程的项目。 **Using**类别显示由特定业务流程的项目。  
  
    ![为业务流程的依赖项](../core/media/dependency-orchestration.jpg "Dependency_Orchestration")  
  
    由于没有其他项目依赖某个业务流程，因此**使用者**业务流程的依存关系类别为空。 但是，在**Using**依存关系模式下图显示了该业务流程将依赖于一个发送端口。 依赖关系的数量显示为超链接，此操作时单击，显示取决于业务流程的发送端口。 请注意，即使在单击超链接以列出发送端口后，依赖关系窗格中仍显示业务流程，并不是发送端口的依赖项统计信息。  
  
    您可以右键单击发送端口，然后单击**查看依赖关系**同样，若要查看发送端口的依存关系表。 任何级别最多可查看依赖关系树。 下图中所示，在窗格顶部的痕迹导航跟踪被显示的您处于依赖关系树的级别。  
  
    ![Bread 依赖关系树的面包屑](../core/media/dependency-breadcrumbs.jpg "Dependency_BreadCrumbs")