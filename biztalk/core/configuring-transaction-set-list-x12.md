---
title: 配置事务集列表 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17e26aac714f05867dab69b6812c109681a47915
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355063"
---
# <a name="configuring-transaction-set-list-x12"></a>配置事务集列表 (X 12)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以定义必须始终包含或排除处理 EDI 交换时的事务集的列表。 本部分提供有关如何创建事务集列表。  
  
> [!NOTE]
>  此处所述的设置也适用于 HIPAA 交换。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-a-transaction-set-list"></a>若要配置事务集列表  
  
1.  创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**事务集列表**。  
  
3.  选择**从列表中支持事务集**选项如果想要创建始终必须处理的事务集的列表。  
  
    > [!NOTE]
    >  如果您通常收到具有特定事务类型，例如 850 交换，可以使用此选项。 在这种情况下，您添加的事务类型设置为列表，以便其他类型的事务集根本不处理。  
  
4.  选择**从列表中排除事务集**选项如果想要创建不得处理的事务集的列表。  
  
    > [!NOTE]
    >  如果您通常接收事务类型变化的交换，可以使用此选项。 在这种情况下，您还将这些事务类型添加到你无法获得任何事务的列表设置。  
  
5.  单击的空单元格中**ST01**列并从下拉列表中选择事务集你想要支持排除类型。  
  
6.  若要从列表中删除事务类型，选择事务类型的行，然后单击**删除**。  
  
7.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)