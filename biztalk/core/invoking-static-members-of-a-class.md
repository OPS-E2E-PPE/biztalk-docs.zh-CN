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
ms.openlocfilehash: 419b83518a9a5cbda54326cf757458afbcdd369b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329834"
---
# <a name="invoking-static-members-of-a-class"></a>调用类的静态成员
默认情况下，规则引擎要求你断言.NET 类来执行策略调用.NET 类的静态成员的实例。 您可以通过更改的值修改此行为**StaticSupport**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**为下表中的值之一。  
  
|StaticSupport 注册表值|规则引擎行为|  
|----------------------------------|--------------------------|  
|0|默认值。 规则引擎遵循 BizTalk Server 2004 模型中，仅当断言.NET 类的实例时，调用静态方法。|  
|1|对象实例不是必需的。 计算或执行规则时，被调用静态方法。|  
|2|对象实例不是必需的。 如果所有参数都是常量，将在策略转换时调用静态方法。 这是一种性能优化，因为即使在条件中的多个规则中使用一次调用静态方法。 请注意，用作操作的静态方法将不会执行转换时，但可能会执行用作参数的静态方法。|  
  
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
> - 您需要在 HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 下查找。 如果此项存在，则可以添加**StaticSupport**此处。  
>   -   另一个选项是将**StaticSupport**中**BTNTsvc [64].exe.config**文件，因为此处的任何设置将覆盖在注册表中。  此外，一个还可以使自变量，此选项是首选因为隔离行为中的更改默认到 BizTalk，而注册表设置是全局性的操作系统。  
  
 **若要更改 StaticSupport 注册表项的值**  
  
1.  单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。  
  
2.  展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BusinessRules**，然后展开**3.0**。  
  
3.  双击**StaticSupport**注册表键，或者右键单击它，然后单击**修改**。