---
title: 配置回退信封属性 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8826041e-02fa-4086-a774-d44a388f42b1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12185022eb7af494fa01a3643d7486fc0c253577
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355676"
---
# <a name="configuring-fallback-envelope-properties-edifact-interchange-settngs"></a>配置回退信封属性（EDIFACT-交换设置）
本部分说明如何配置为传出 EDIFACT 消息信封。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-the-interchange-envelope"></a>若要配置交换信封  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。  
  
2. 在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**信封**.  
  
3. 有关**处理优先级代码 (UNB8)**，输入最少一个字符，最多为 1 个字符的字母数字值。 这是一个可选字段。  
  
4. 有关**通信协议 (UNB10)**，输入包含最少一个字符，最多为 35 个字符的字母数字值。 这是一个可选字段  
  
5. 选择**测试指示器 (UNB11)** 以指示由生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。  
  
6. 选择**应用 UNA 段 （字符串服务建议）** 生成要发送交换的 UNA 段。 如果选中此选项，然后**UNA6**不能为空并**UNA 6 后缀**不能为**None**。  
  
   > [!NOTE]
   >  您指定**UNA6**并**UNA6 后缀**中**字符集和分隔符**页中所述[配置回退字符集和分隔符属性 (EDIFACT)](../core/configuring-fallback-charset-and-separator-properties-edifact.md)。  
  
7. 选择**应用 UNG 段 （功能组标头）** 在传出消息的功能组标头中创建分组段。  
  
8. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 EDIFACT 后备协议属性](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)