---
title: 如何包括和排除架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9206458-e5d6-48d7-87a6-9471ba60dca7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfa1f610cef6e67f17ca14737c6ca853dd5cd16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254341"
---
# <a name="how-to-include-and-exclude-schemas"></a>如何包括和排除架构
架构文件可以存在于 BizTalk 项目文件夹中，但并不包括在该项目中。 此类架构称为从项目中排除。 生成 BizTalk 项目时不会编译排除的架构。 本主题将介绍在 BizTalk 项目中包括已排除的架构以及从 BizTalk 项目中排除架构所需的步骤。  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a>在 BizTalk 项目中包括架构  
  
1.  在解决方案资源管理器中，打开包含要包括在其项目文件夹中的架构的 BizTalk 项目。  
  
2.  如果所有文件都未已都显示，在**项目**菜单上，单击**显示所有文件**。  
  
3.  在解决方案资源管理器，右键单击你想要包括，然后单击排除的架构**包括在项目**。  
  
     解决方案资源管理器中先前排除的架构的图标从空轮廓变为正常的架构图标。  
  
4.  （可选） 在**项目**菜单上，单击**显示所有文件**若要隐藏的项目文件夹中不包括在项目的所有文件。  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a>从 BizTalk 项目中排除架构  
  
-   在解决方案资源管理器，右键单击你想要排除，并依次架构**从项目中排除**。  
  
     此时该架构将从 BizTalk 项目中排除。  
  
    > [!NOTE]
    >  从项目中排除某架构时，该架构不会从文件系统中删除。 但是，生成项目时不会包括该架构。 你可以选择是否在项目文件夹中要排除的文件，通过切换**显示所有文件**在解决方案资源管理器窗口顶部的工具。  
  
    > [!NOTE]
    >  在将架构文件从项目中删除时，如果也要将架构从文件系统中删除，则需要删除架构。 有关删除架构的详细信息，请参阅[删除架构](../core/how-to-delete-schemas.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管理架构在项目中](../core/managing-schemas-within-projects.md)