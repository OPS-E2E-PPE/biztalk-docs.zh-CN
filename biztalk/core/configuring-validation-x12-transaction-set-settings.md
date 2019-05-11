---
title: 配置验证 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0245be7f-d212-43b1-bfef-cbcbd851b5c0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdac815ff28bef0f609f4629c9e23c53c59dce8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390482"
---
# <a name="configuring-validation-x12-transaction-set-settings"></a>配置验证（X12--事务集设置）
事务集验证设置定义 BizTalk Server 如何验证从参与方接收的事务集。 作为验证设置的一部分可以指定 BizTalk Server 将对传入的交换执行哪种类型的验证  
  
> [!NOTE]
>  本主题还适用于 HIPAA 验证设置。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-validation-settings"></a>若要配置验证设置  
  
1.  创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**验证**。  
  
3.  在网格中，可以定义不同的事务集的不同的验证设置。 在中**验证**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**默认**|选中复选框，以定义默认验证设置。|  
    |**事务类型**|单击空单元格的列中并从下拉列表中选择事务类型。|  
    |**Edi 类型验证**|选择此选项可启用对交换接收方的 EDI （数据元素） 验证。 此验证对事务集数据元素，验证数据类型、 长度限制以及空数据元素和尾部分隔符执行 EDI 验证。 有关详细信息，请参阅[EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)。 **注意：** 即使未选择此属性，如果在架构批注中开启，将执行跨字段/段验证。|  
    |**扩展的验证**|选择此选项可启用从交换发送方接收的交换的扩展 (BizTalk XSD) 验证。 这包括验证字段长度、 可选性和重复计数除了验证 XSD 数据类型。 有关详细信息，请参阅[扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)。 **注意：** 您可以选择此复选框才**Edi 类型验证**处于选中状态。|  
    |**允许前导和尾随零及空格**|选择此选项可以指定从某方收到的 EDI 交换将会通过验证，是否某个 EDI 交换中的数据元素不符合其长度要求由于前导 （或尾随） 零或尾随空格，但符合其长度要求删除它们。 **注意：** 您可以选择此复选框才**Edi 类型验证**处于选中状态。|  
    |**尾部分隔符策略**|-选择**不允许**如果您不想要从交换发送方接收的交换中允许尾部分隔符。 如果该交换包含尾部分隔符，会将它声明无效。<br />-选择**可选**以接受包含或不包含尾随分隔符的交换。<br />-选择**必需**如果收到的交换必须包含尾部分隔符。|  
  
     可以添加你想要定义特定交换的验证设置的所有行。  
  
     若要删除验证设置，选择的行，然后单击**删除**。  
  
    > [!NOTE]
    >  在网格中编辑属性可能有点困难。 相反，可以选择要进行编辑，然后编辑中的相同属性的行**编辑所选行**部分。 此处提供的设置将反映在所选行。  
  
4.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)