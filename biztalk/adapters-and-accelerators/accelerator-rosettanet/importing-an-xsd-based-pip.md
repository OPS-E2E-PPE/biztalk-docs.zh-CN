---
title: 导入基于 XSD 的 PIP |Microsoft 文档
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
ms.openlocfilehash: 7d8865d7a75bdb06895b963b8269ed457cd5804f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961651"
---
# <a name="importing-an-xsd-based-pip"></a>导入基于 XSD 的 PIP
虽然 RosettaNet.org 所提供的大部分 PIP 是基于 DTD 的，但较新的 PIP 是基于 XSD 的。 以下过程描述如何导入基于 XSD 的 PIP。  
  
### <a name="to-import-an-xsd-based-pip"></a>导入基于 XSD 的 PIP  
  
1.  在 RosettaNet.org 从下载基于 XSD 的 PIP.zip 文件[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)或从在 CIDX.org [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)。 从该 .zip 文件中提取文件。 你所需要的文件位于 XML 文件夹的子文件夹中。  
  
2.  打开 Visual Studio。 创建新 BizTalk 项目。  
  
3.  打开 Windows 资源管理器，转到在步骤 1 中提取的 XML 文件夹。 选择 XML 文件夹下的第一个文件夹，将其拖到 Visual Studio 的解决方案资源管理器中，然后将其放到您的项目中。 对 XML 文件夹中的每个子文件夹重复上述步骤，在你的项目中创建相同的文件夹结构。  
  
    > [!NOTE]
    >  对于 PIP7c7 PIP，这些文件夹应包含 Domain、Interchange、System 和 Universal 文件夹。 对于此 PIP，你的项目应包含 Domain、Interchange、System 和 Universal 文件夹及这些文件夹的内容。  
  
4.  如果 System 文件夹中有 .xsd 文件，则请在解决方案资源管理器中选择该文件，然后更改属性页中列出的命名空间，以使其不包含字符串“.System”。 例如对于 PIP7c7 PIP，可以将命名空间更改为“PIP7c7._System”。 对 System 文件夹中的每个 .xsd 文件重复上述步骤。 如果不更改命名空间，你将收到以下错误或类似的错误：  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  查看所有.xsd 文件，以确保\<架构\>e，根节点类型名称不相同。 例如，对于 PIP7C7 PIP PartnerIdentification.xsd 通用文件夹中的具有 PartnerIdentification 的类型名称为\<架构\>（时 PartnerIdentification.xsd 在解决方案资源管理器中选择） 以及PartnerIdentification 根节点。 若要更正此错误，请在解决方案资源管理器中选择 PartnerIdentification.xsd，然后在属性页中更改类型名属性，以使其类型名与 PartnerIdentification 根结点不同。 例如，可将类型名更改为“_PartnerIdentification”。 如果不执行此步骤，则在尝试生成项目时将会收到以下错误：  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  错误列表中的“文件”列将指出那些文件包含此问题。  
  
6.  生成然后部署项目。