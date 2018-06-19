---
title: 如何将 XDR 架构迁移到 XSD 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25971619"
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a>如何将 XDR 架构迁移到 XSD 架构
如果是从早期版本的 BizTalk Server 迁移架构，则需要将精简 XML 数据 (XDR) 架构转换为 XML 架构定义 (XSD) 语言架构。 本主题介绍了必需的步骤。  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a>从 XDR 架构生成 XSD 架构  
  
1.  在 **解决方案资源管理器**, ，右键单击相关的 BizTalk 项目，指向 **添加**, ，然后单击 **添加生成的项**。  
  
2.  在**添加生成项- \< *BizTalk ProjectName* \>** 对话框中，在**模板**部分中，单击**生成架构**，然后单击**添加**。  
  
3.  在 **生成架构** 对话框中，在 **文档类型** 列表中，选择 **XDR 架构**。  
  
4.  单击 **浏览**, ，找到你想要迁移，并依次 XDR 架构文件 **确定**。  
  
     此时，将从指定的 XDR 架构文件生成与该文件同名并具有 .xsd 扩展名的新架构，然后在 BizTalk 编辑器中打开该架构。  
  
> [!NOTE]
>  不要使用 C# 保留字以及 .NET Framework 类型和命名空间名称（例如 System）作为架构根节点名称或文件名。  
  
## <a name="see-also"></a>另请参阅  
 [管理架构在项目中](../core/managing-schemas-within-projects.md)   
 [迁移平面文件记录](../core/migrating-flat-file-records.md)