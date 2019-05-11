---
title: 导入基于 XSD 的 PIP |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8d1a0d6b4fe835a38dc5eaf19a328b14e0d288f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283674"
---
# <a name="importing-an-xsd-based-pip"></a>导入基于 XSD 的 PIP
尽管大部分 RosettaNet.org 所提供的 PIP 是基于 DTD 的、 较新的 PIP 是基于 XSD 的。 以下过程描述如何导入基于 XSD 的 PIP。  
  
### <a name="to-import-an-xsd-based-pip"></a>若要导入基于 XSD 的 PIP  
  
1.  从 rosettanet.org 下载得到处下载基于 XSD 的 PIP 的.zip 文件[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)或在 cidx.org [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361)。 从.zip 文件中提取文件。 所需的文件将 XML 文件夹的子文件夹中。  
  
2.  打开 Visual Studio。 创建新的 BizTalk 项目。  
  
3.  打开 Windows 资源管理器，然后转到在步骤 1 中提取的 XML 文件夹。 选择 XML 文件夹下的第一个文件夹，将其拖到解决方案资源管理器在 Visual Studio 中，并放入项目。 重复的每个子文件夹中的 XML 文件夹中，在你的项目中创建的相同文件夹结构。  
  
    > [!NOTE]
    >  对于 PIP7c7 PIP 这些文件夹将包括域、 交换、 系统和通用文件夹。 对于此 PIP，你的项目应包含域、 交换、 系统和通用文件夹和其内容。  
  
4.  如果系统文件夹中没有一个.xsd 文件，在解决方案资源管理器中选择它并更改，以便它不包含字符串的属性页中列出的命名空间"。系统"。 例如，对于 PIP7c7 PIP，可以更改命名空间为"PIP7c7._System"。 每个.xsd 文件重复系统文件夹中。 如果不更改命名空间，你将收到以下或类似的错误消息：  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  检查所有.xsd 文件，以确保\<架构\>类型名与根节点的类型名不相同。 例如，对于 PIP7C7 PIP 的 Universal 文件夹中 PartnerIdentification.xsd 具有 TypeName partneridentification 两个\<架构\>（当 PartnerIdentification.xsd 在解决方案资源管理器中选择） 以及PartnerIdentification 根结点。 若要更正此问题，在解决方案资源管理器中选择 PartnerIdentification.xsd，然后在属性页中更改的 TypeName 属性，以便它不包含类型名与 PartnerIdentification 根结点。 例如，更改类型名称为"_PartnerIdentification"。 如果不执行此步骤，将收到以下错误，当你尝试生成项目时：  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  错误列表中的文件列将指示哪些文件会出现此问题。  
  
6.  生成，然后部署该项目。