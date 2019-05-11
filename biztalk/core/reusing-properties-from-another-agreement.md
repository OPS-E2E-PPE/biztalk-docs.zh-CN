---
title: 重用其他协议的属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b304af8fbc455a3a18b21774ebc9f1b25e55257
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395595"
---
# <a name="reusing-properties-from-another-agreement"></a>重用其他协议的属性
可以重复使用协议之间的属性。 这样可以节省大量的时间时大多数或所有新协议的属性将与这些现有的协议相同。 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server 中的用户界面，可导出到 XML 模板文件的协议。 然后可以导入该 XML 模板以重复使用相同的协议属性。  
  
 导出协议到 XML 模板捕获最，而不是全部，协议的属性。 以下属性将*不*导出到 XML 模板文件：  
  
- 中的所有属性**常规属性**页面**常规**选项卡。  
  
- 中的所有属性**联系人**页面**常规**选项卡。  
  
- 中的所有属性**附加属性**页面**常规**选项卡。  
  
- 从与标识符相关的设置**标识符**页的单向协议选项卡。这些是：  
  
  -   **对于 X12**:ISA5、 ISA6、 ISA7、 ISA8 和其他协议解析程序设置  
  
  -   **对于 EDIFACT**:UNB 2.1、 UNB 2.2、 UNB 3.1，UNB 3.2 和其他协议解析程序设置  
  
  -   **适用于 AS2**:AS2-To、as2-From、 和其他协议解析程序设置  
  
- 发送端口关联**发送端口**协议中适用于 X12 和 AS2 的单向协议选项卡页。  
  
  上面列出的属性，以外的下列属性将导出到 XML 模板文件：  
  
- 所有与编码协议 (X12、 EDIFACT 或 AS2) 相关的设置。  
  
- 所有与批处理相关的设置 （而不是批处理 ID)。  
  
> [!NOTE]
>  将属性复制到目标协议时，将覆盖所有适用的属性。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将协议属性导出为 XML 文件](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [从 XML 文件导入协议属性](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)