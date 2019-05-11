---
title: 配置回退信封属性 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e9b05ea-2a0f-42d6-adc2-c1f1f2b7a993
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6e7af661992db4067bd62d53b58322c486ec57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355669"
---
# <a name="configuring-fallback-envelope-properties-x12-interchange-settings"></a>配置回退信封属性（X 12 交换设置）
X12 交换信封生成设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成要发送到接收方的 X12 编码交换的信封。 在此备用协议中，您将定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成在它发送到参与方的 X12 编码交换的 ISA 段。 ISA 段是 X12 编码交换的交换控制标头。  
  
> [!NOTE]
>  有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]字母数字 ISA 字段的长度固定的运行时。 但是，对于[!INCLUDE[TPM](../includes/tpm-md.md)]用户界面，则可以为字母数字 ISA 字段输入单个字符。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将填充这些字段用尾随空格字符，以确保符合标准要求。  
> 
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换信封生成。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-define-the-envelope"></a>若要定义信封  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。  
  
2. 在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**信封**.  
  
3. 下**ISA11 用法**，保留**标准标识符**选择指定一个标准标识符而不是重复分隔符，并从下拉列表中选择标准标识符的值。 选择**重复分隔符**若要指定重复分隔符而非标准标识符，然后再为此重复分隔符输入单个字符。 用于分隔事务集内重复的段的重复分隔符仅限于 ASCII 字符集中的值。  
  
4. 有关**控制版本号 (ISA12)**，选择的 x12 标准，供版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于生成传出交换。  
  
5. 有关**用法指示符 (ISA15)**，选择以指示生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是信息、 生产数据还是测试数据。  
  
6. 单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [为交换处理配置 X12 后备协议属性](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)