---
title: 验证消息实例使用的架构 XSD |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c8c234ecdb79b8aa2e15c99717396199514e29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299949"
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a>验证消息实例使用的架构 XSD
本主题介绍如何验证消息实例使用的架构 XSD 文件之一的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]内置到 Rnpip 程序集文件。  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a>若要验证消息实例使用的架构 XSD  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**，依次指向**打开**，然后单击**项目**。  
  
3.  找到*\<驱动器\>* \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。  
  
4.  在解决方案资源管理器，展开**Rnpip**，右键单击架构 XSD，想要用于验证消息实例，然后依次**属性**。  
  
5.  在属性页对话框中，单击**输入实例文件名**，找到包含该文件的文件夹、 选择消息实例 XML 文件，并单击**打开**。  
  
6.  单击“确定” 。  
  
7.  在解决方案资源管理器中右键单击架构 XSD，想要用于验证消息实例，然后依次**验证实例**。  
  
## <a name="see-also"></a>请参阅  
 [修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)   
 [使用 PIP](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)