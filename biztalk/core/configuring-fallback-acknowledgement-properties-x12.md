---
title: 配置回退确认属性 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ba465598f94f5f9ff41e74d50962a71b0ad979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391251"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a>配置回退确认属性 (X 12)
在后备协议中，您可以指定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]响应从参与方和类型的确认返回到参与方接收的 X12 编码交换而生成确认。 本部分将说明了如何执行此操作。  
  
> [!NOTE]
>  此处所述的确认属性同样适用于 HIPAA 确认。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-x12-ack-properties"></a>若要配置 X12 确认属性  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**确认**.  
  
3. 选择**预期的 TA1**向交换发件人返回技术 (TA1) 确认。  
  
4. 选择**预期的 997**向交换发件人返回功能 (997) 确认。  
  
5. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)