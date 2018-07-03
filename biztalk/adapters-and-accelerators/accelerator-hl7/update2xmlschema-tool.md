---
title: Update2XMLSchema 工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108bc63536e84dd18cd738fbc6ec10d1e07c404b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978134"
---
# <a name="update2xmlschema-tool"></a>Update2XMLSchema 工具
Update2XMLSchema 工具，可修改 HL7 2.xml 架构以使用 BizTalk 编辑器。 这是必需的因为 Microsoft 中无法正常工作某些 HL7 2.xml 架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]无需修改即可。 修改后的架构，该工具将它们放在此架构文件夹位置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]已安装，例如， *\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\Templates\Schemas。  
  
 需要更新手动运行 Update2XMLSchema 工具生成的架构的某些字段。 请参阅[所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)有关这些架构的列表。  
  
## <a name="syntax"></a>语法  
 此工具位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\2XML 实用程序。 在命令提示符处使用以下命令运行此工具：  
  
```  
Update2XMLSchema /s /v  
```  
  
 下表列出了要使用此命令使用的参数。  
  
|参数|“属性”|ReplTest1|  
|---------------|----------|-----------|  
|*S*|数据源|原始的 HL7 架构的完整路径|  
|*V*|版本|2.XML 架构的版本： 2.3.1、 2.4 或 2.5|  
  
## <a name="example"></a>示例  
  
-   如果你想要修改版本 2.3.1 2.xml 架构位于 c:\231XML\v231\xsd 目录中，你将在命令提示符下键入以下命令：  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a>本节内容  
  
-   [需要手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)