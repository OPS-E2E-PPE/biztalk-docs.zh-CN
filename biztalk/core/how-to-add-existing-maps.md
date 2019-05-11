---
title: 如何添加现有映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a566a76d1d42d099e1825af7d6774644bb9049d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387293"
---
# <a name="how-to-add-existing-maps"></a>如何添加现有映射
可能存在你想要将现有的映射添加到 BizTalk 项目。 这样做之前必须确保映射的源和目标架构都包含向其中添加映射中，则在 BizTalk 项目中或者，通过相应的.NET 程序集引用。  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a>若要将现有的映射添加到 BizTalk 项目  
  
1. 右键单击解决方案资源管理器中的 BizTalk 项目，指向**外**，然后单击**现有项**。  
  
2. 在中**添加现有项**对话框中，浏览到包含要添加、 选择它，然后单击该映射的文件夹**添加**。  
  
    在 BizTalk 映射器中打开该映射。 在解决方案资源管理器中的当前 BizTalk 项目的小孩也会出现新添加的映射。  
  
   > [!NOTE]
   >  如果浏览到的文件夹不是 BizTalk 项目文件夹，在项目文件夹中，创建一份所添加的映射，并已添加到项目的映射此副本。 对此副本，不到其他文件夹中的原始映射进行映射的后续更改。  
   > 
   > [!IMPORTANT]
   >  BizTalk 映射只能通过 BizTalk 映射器，托管在 Microsoft 内打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。 如果您双击 Windows 资源管理器的新实例中某个映射[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]将打开，然后该映射将会打开 BizTalk 映射器提供了相应的架构已正确加载。  
   > 
   > [!NOTE]
   >  如果现有映射中包含自定义 functoid，然后在负载测试相应的 Dll 必须将复制到文件夹"%BTSINSTALLPATH%\Developer Tools\Mapper Extensions"。 否则，映射将不会加载和由于加载自定义 functoid 失败将引发错误。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的映射](../core/managing-maps-within-projects.md)   
 [开发自定义 Functoid](../core/developing-custom-functoids.md)