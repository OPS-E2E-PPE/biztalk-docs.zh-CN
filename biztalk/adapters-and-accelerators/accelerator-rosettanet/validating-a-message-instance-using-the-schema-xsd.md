---
title: "验证使用 XSD 架构的消息实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a4e0b08e3bbe9e29b3417fd6e53475fd98483c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a>验证使用 XSD 架构的消息实例
本主题介绍如何使用 Microsoft?[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 内置到 RNPIP 程序集文件中的架构 XSD 文件之一来验证消息实例。  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a>用架构 XSD 验证消息实例  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**，指向**打开**，然后单击**项目**。  
  
3.  找到*\<驱动器 >*files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。  
  
4.  在解决方案资源管理器，展开**RNPIPs**，右键单击你想要使用以验证消息实例，然后单击的 XSD 架构**属性**。  
  
5.  在属性页对话框中，单击**输入实例 Filename**，找到包含文件的文件夹、 选择消息实例 XML 文件，然后单击**打开**。  
  
6.  单击 **“确定”**。  
  
7.  在解决方案资源管理器，右键单击你想要使用以验证消息实例，然后单击的 XSD 架构**验证实例**。  
  
## <a name="see-also"></a>另请参阅  
 [修改在 RNPIPs 现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)   
 [使用 Pip](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)