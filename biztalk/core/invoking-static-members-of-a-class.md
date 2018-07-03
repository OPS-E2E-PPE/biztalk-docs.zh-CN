---
title: 调用类的静态成员 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cb6a673fcf7fb363de678eceefd62802a063ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022075"
---
# <a name="invoking-static-members-of-a-class"></a>调用类的静态成员
默认情况下，规则引擎要求你断言 .NET 类的一个实例来执行一项策略，该策略可调用 .NET 类的静态成员。 您可以通过更改的值修改此行为**StaticSupport**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**为下表中的值之一。  
  
|StaticSupport 注册表值|规则引擎行为|  
|----------------------------------|--------------------------|  
|0|默认值。 规则引擎遵循 BizTalk Server 2004 模型，在该模型中，只有断言 .NET 类的某个实例后才能调用静态方法。|  
|@shouldalert|对象实例不是必需的。 将在评估或执行规则时调用静态方法。|  
|2|对象实例不是必需的。 如果所有参数都是常数，则将在策略转换时调用静态方法。 这是一种性能优化，因为尽管静态方法在条件中的多个规则中使用，但只会调用一次。 请注意，用作操作的静态方法将不能在转换时执行，不过用作参数的静态方法可以在转换时执行。|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a>添加和更改 StaticSupport 注册表项  
 如果没有看到**StaticSupport**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，应将其添加，请执行以下步骤。  
  
 **若要添加 StaticSupport 注册表项**  
  
1. 单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。  
  
2. 展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BusinessRules**，然后选择**3.0**。  
  
3. 在右窗格中，右键单击，指向**新建**，然后单击**DWORD 值**。  
  
4. 有关**名称**，类型**StaticSupport**。  
  
   如果**StaticSupport**注册表项已存在，并且你需要将其值更改，请执行以下步骤。  
  
> [!IMPORTANT]
>  如果 BizTalk 安装在 64 位计算机上，则可以添加**StaticSupport**注册表项，使用以下选项之一：  
> 
> - 你需要在 HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 下查找。 如果此项存在，则可以添加**StaticSupport**此处。  
>   -   另一个选项是将**StaticSupport**中**BTNTsvc [64].exe.config**文件，因为此处的任何设置将覆盖在注册表中。  此外还可以得出的结论就是，此选项是一个首选选项，因为它会将默认行为中的更改仅隔离到 BizTalk，而注册表设置是针对操作系统的全局设置。  
  
 **若要更改 StaticSupport 注册表项的值**  
  
1.  单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。  
  
2.  展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BusinessRules**，然后展开**3.0**。  
  
3.  双击**StaticSupport**注册表键，或者右键单击它，然后单击**修改**。