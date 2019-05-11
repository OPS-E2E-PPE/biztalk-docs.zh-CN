---
title: 如何包括和排除架构 |Microsoft Docs
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
ms.openlocfilehash: e05cdb76ce64fae8b75b212711e805c04ac473a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384947"
---
# <a name="how-to-include-and-exclude-schemas"></a>如何包括和排除架构
架构文件可以存在于 BizTalk 项目文件夹，并不会包含在该项目中。 此类架构称为从项目中排除。 生成 BizTalk 项目时，不会编译排除的架构。 本主题介绍在 BizTalk 项目中，包括已排除的架构以及从 BizTalk 项目中排除架构所需的步骤。  
  
### <a name="to-include-a-schema-in-a-biztalk-project"></a>若要在 BizTalk 项目中包括的架构  
  
1.  在解决方案资源管理器，打开包含要在其项目文件夹中包含的架构的 BizTalk 项目。  
  
2.  如果所有文件都不已都显示，请在**项目**菜单上，单击**显示所有文件**。  
  
3.  在解决方案资源管理器，右键单击你想要包括，然后单击已排除的架构**包括在项目**。  
  
     在解决方案资源管理器中先前排除的架构的图标从空轮廓变为正常的架构图标。  
  
4.  （可选） 在**项目**菜单上，单击**显示所有文件**隐藏项目文件夹中不包含在项目的所有文件。  
  
### <a name="to-exclude-a-schema-from-a-biztalk-project"></a>若要从 BizTalk 项目中排除架构  
  
-   在解决方案资源管理器，右键单击你想要排除，然后单击架构**从项目中排除**。  
  
     该架构现在从 BizTalk 项目中排除。  
  
    > [!NOTE]
    >  从项目中排除架构，架构是不会删除从文件系统。 但是，生成项目时，则不包含架构。 您可以选择是否要在项目文件夹中显示排除的文件，通过切换**显示所有文件**解决方案资源管理器窗口顶部的工具。  
  
    > [!NOTE]
    >  如果你想要从文件系统，以及从项目中删除的架构文件中删除架构，您需要删除该架构。 有关删除架构的详细信息，请参阅[删除架构](../core/how-to-delete-schemas.md)。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)