---
title: "重复使用来自另一个协议属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7db2118f372014a3e8f108c1ff2273bc5aad976
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="reusing-properties-from-another-agreement"></a>重用其他协议的属性
您可以重复使用协议之间的属性。 当新协议的大多数或所有属性与现有协议的属性相同时，此操作可以节省大量时间。 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server 中的用户界面，可导出到 XML 模板文件的协议。 然后，您可以导入该 XML 模板以重复使用相同的协议属性。  
  
 导出协议到 XML 模板可捕获该协议的大多数属性，但并非全部。 以下属性将*不*导出到 XML 模板文件：  
  
-   中的所有属性**常规属性**页面**常规**选项卡。  
  
-   中的所有属性**联系人**页面**常规**选项卡。  
  
-   中的所有属性**其他属性**页面**常规**选项卡。  
  
-   从标识符相关设置**标识符**的单向协议选项卡中的页。这些是：  
  
    -   **对于 X12**: ISA5、 ISA6、 ISA7、 ISA8，和其他协议解析程序设置  
  
    -   **对于 EDIFACT**: UNB 2.1、 UNB 2.2、 UNB 3.1、 UNB 3.2 和其他协议解析器设置  
  
    -   **对于 AS2**: AS2-到 AS2-从，和其他协议解析程序设置  
  
-   发送端口关联从**发送端口**页在单向协议选项卡中的 X12、 EDIFACT 和 AS2 协议。  
  
 除以上所列属性之外，以下属性将被导出至 XML 模板文件：  
  
-   所有与编码协议（X12、EDIFACT 或 AS2）相关的设置。  
  
-   所有与批相关的设置（批 ID 除外）。  
  
> [!NOTE]
>  在复制属性到目标协议时所有相应属性都将被覆盖。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将协议属性导出为 XML 文件](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [从 XML 文件导入协议属性](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)