---
title: 如何保存、 重命名，并关闭架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13944689885ea504679591fcaabb2f442c486de1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334843"
---
# <a name="how-to-save-rename-and-close-schemas"></a>如何保存、 重命名，并关闭架构
在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，架构是 XML 架构定义 (XSD) 语言文件，并位于具有.xsd 扩展名的文件系统上。 当使用 BizTalk 编辑器开发架构时，将定期需要保存和关闭架构文件，并有时可能需要将其重命名。 本主题介绍执行这些基本操作所需的步骤。  
  
### <a name="to-save-a-schema"></a>若要保存架构  
  
1. 如有必要，激活 BizTalk 编辑器架构通过单击 Microsoft 中主编辑窗口顶部相应的选项卡保存[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 上**文件**菜单上，单击 * * 保存 *\<架构名称\>* * *。  
  
    如果架构具有未保存的更改，其名称显示在主编辑窗口顶部的选项卡上将无法再最终有一个星号 （*），用于指示未保存的更改。  
  
> [!NOTE]
>  您可以通过单击保存以新名称的架构**保存*\<名称的架构\>* 作为**上**文件**菜单。  
  
> [!NOTE]
>  您可以将架构作为保存所有更改的项目在项目中通过单击操作的一部分**全部保存**上**文件**菜单。  
  
#### <a name="to-rename-a-schema"></a>若要重命名架构  
  
1.  在解决方案资源管理器，右键单击你想要重命名，然后单击架构**重命名**。  
  
2.  中将出现在解决方案资源管理器中的架构的位置的编辑框，键入新名称的架构，或更改其现有的名称，，然后按 ENTER。  
  
> [!NOTE]
>  您可能还需要更改**类型名称**进行重命名的架构。 您更改**类型名称**通过选择**架构**中的解决方案资源管理器并输入中的新名称**类型名称**属性窗口中。  
  
> [!IMPORTANT]
>  不应重命名任何正由另一个架构的架构。 这包括由其他架构，以及已为其建立升级的属性架构已包括、 导入，或重新定义的架构。 如果这样做，正在使用的架构不能查找重命名的架构，因为它包含的名称将不再准确。  
  
> [!NOTE]
>  某些项目成员文件，例如架构文件的名称选项可能会导致编译错误由于冲突而进行更高版本上使用 C# 保留字和.net Framework 类型和命名空间名称 （例如"系统"）。 有关架构的示例包括 schema.xsd、 XmlContent 和 RootNodes。 这是因为**类型名称**属性默认为基 （非扩展名） 部分**Filename**属性。 可以通过显式更改的值来解决这种类型的编译错误**类型名称**为不冲突的属性。  
  
#### <a name="to-close-a-schema"></a>若要关闭架构  
  
1. 如有必要，激活 BizTalk 编辑器中的架构通过单击 Microsoft 中主编辑窗口顶部相应的选项卡关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 在 **“文件”** 菜单上，单击 **“关闭”**。  
  
    对已关闭的架构关闭 BizTalk 编辑器。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)