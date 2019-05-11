---
title: 配置本地主机设置 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1cf8696-d1f4-49aa-aa0a-ecf66f55e01d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13c8703fdcd3007c9fbfd6311c2baf81569aa7a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355266"
---
# <a name="configuring-local-host-settings-edifact-interchange-settings"></a>配置本地主机设置 （EDIFACT-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可划分为两个类别： 接收方设置 （用于传入交换） 和发件人的设置 （适用于传出交换）。 作为接收方设置的一部分，可以指定是否将拆分为事务集或保留传入的批。 如果保留，可以指定 BizTalk Server 将挂起交换或事务集出错时。 作为发送方设置的一部分，可以指定如何为传出消息生成控制编号。  
  
> [!IMPORTANT]
>  以下属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果你清除了**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**参与方 a 的复选框  
> 
> - 下的所有属性**发件人的设置**部分。  
> 
>   以下属性中的相同页上将禁用与此类似，**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
> 
> - 下的所有属性**接收方设置**部分。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-configure-local-host--receivers-settings"></a>若要配置本地主机 – 接收方设置  
  
1. 创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**本地主机设置**。  
  
3. 在中**EDIFACT 确认**部分，若要指定要在确认中使用的事务集参考编号的前缀、 参考编号和后缀的范围输入一个值。  
  
    单击**重置**重置当前事务集参考编号为下限。 选择**重置为下限值超出界限时**具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将的参考编号重置为较低范围值限制，如果超出最大限制。  
  
4. 清除**将确认路由到发送管道请求-响应接收端口**返回通过单独确认的发送端口。 保留选择了该属性上与双向请求-响应关联的发送端口返回确认接收端口。  
  
5. 清除**屏蔽安全/授权/密码信息**禁用屏蔽上下文属性以防止信息泄漏中的授权/密码安全信息 （UNB6.1 和 UNB6.2 字段）。  
  
   > [!NOTE]
   >  当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息，它将 UNB 标头升级到消息的上下文。 如果不屏蔽，上下文中的安全信息将可供具有管理权限的任何人。 为了屏蔽此信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]替代信息中的每个字符**#** 字符。 这是一个单向过程： **#** 字符不能转换为实际的字符。  
  
6. 在中**入站批处理选项**下拉列表中，执行以下操作：  
  
   1.  选择默认选项**将交换拆分为事务集-出错时挂起事务集**以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将向事务集应用相应的信封和事务集文档路由到 MessageBox。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集。  
  
   2.  选择**将交换拆分为事务集-出错时挂起交换**以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将向事务集应用相应的信封和事务集文档路由到 MessageBox。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
   3.  选择**保留交换-出错时挂起交换**以指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 使用此选项时，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
   4.  选择**保留交换-出错时挂起事务集**以指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 使用此选项，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集，同时继续处理所有其他事务集。  
  
       > [!NOTE]
       >  如果选择**保留交换-出错时挂起交换**或**保留交换-出错时挂起事务集**，在属性设置**ISA 段定义**并**GS 和 ST 段定义**页 （用于确定 BizTalk Server 将如何创建传出交换的 ISA、 GS 和 ST 标头） 不适用。 当发送管道对其进行处理用于发送保留交换、 组和要保留的交换中存在的事务集标头。  
  
### <a name="to-configure-local-host--senders-settings"></a>若要配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (UNB5)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。 输入具有最小为 1 和最大为 999999999 的数值。 这是必填字段。  
  
    > [!NOTE]
    >  第一个字段 (**UNB5.1**) 是前缀; 第二个和第三字段 (**UNB5.2**) 包含要用作交换控制编号; 和第四个字段的编号范围 (**UNB5.3**)是的后缀。 前缀和后缀是可选的;控制编号是必需的。 对于每个新的消息; 递增的控制编号前缀和后缀保持不变。 最大字符数是 14 控制编号的前缀和后缀，13 和 14 个所有三个字段结合使用。  
    >   
    >  若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
2.  有关**组控制编号 (UNG5)**、 输入前缀、 参考编号范围和 BizTalk Server 应为它发送的第一个交换的组控制编号使用的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNG5.1**) 是前缀; 第二个和第三字段 (**UNG5.2**) 包含要用于组控制编号; 和第四个字段的编号范围 (**UNG5.3**) 是后缀。 前缀和后缀是可选的;控制编号是必需的。 对于每个新消息递增的控制编号，直到达到最大值;前缀和后缀保持不变。 只允许使用数字中**UNG5.2**。 最大字符数是 14 控制编号的前缀和后缀，13 和 14 个所有三个字段结合使用。  
    >   
    >  若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
3.  有关**消息标头 (UNH)**，单击**应用新 ID**、 输入前缀、 参考编号范围，输入和输入 BizTalk Server 应为事务集参考编号使用的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNH1.1**) 是前缀; 第二个和第三字段 (**UNH1.2**) 是参考编号范围; 和第四个字段 (**UNH1.3**) 是后缀。 前缀和后缀是可选的;引用编号是必需的。 对于每个新的消息; 递增的参考编号前缀和后缀保持不变。 参考编号的默认值范围是 1 到 99999999999999。 只允许使用数字中**UNH1.2**。 最大字符数是 14 控制编号的前缀和后缀，13 和 14 个所有三个字段结合使用。  
    >   
    >  若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。  
  
4.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)