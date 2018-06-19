---
title: 配置本地主机设置 （EDIFACT 交换设置） |Microsoft 文档
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
ms.openlocfilehash: 0b93833e8143f1b6706d86295e3f5db8292bc6c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234685"
---
# <a name="configuring-local-host-settings-edifact-interchange-settings"></a>配置本地主机设置（EDIFACT-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。 在接收方的设置中，可以指定传入的批是拆分为事务集还是保留。 如果保留，可以指定 BizTalk Server 在发生错误时是否挂起交换或事务集。 作为发送方设置的一部分，可以指定为传出消息生成控制编号的方式。  
  
> [!IMPORTANT]
>  以下属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框 a 方。  
>   
>  -   下的所有属性**发件人设置**部分。  
>   
>  同样，将以下属性禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
>   
>  -   下的所有属性**接收方设置**部分。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host--receivers-settings"></a>配置本地主机 – 接收方设置  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**本地主机设置**。  
  
3.  在**EDIFACT ACK**部分中，指定事务集引用编号，以确认中, 使用输入的值的前缀、 引用编号和后缀的范围。  
  
     单击**重置**重置当前事务集引用编号为下限。 选择**重置为下限超出界限时**能够[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将引用编号重置为较低范围值限制，如果超出最大限制。  
  
4.  清除**路由 ACK 发送管道请求-响应接收端口**返回通过单独确认发送端口。 如果将该属性保留为选中状态，则会在与双向请求-响应接收端口关联的发送端口上返回确认。  
  
5.  清除**屏蔽安全/授权/密码信息**禁用屏蔽上下文属性，以防止信息泄漏中的授权/密码安全信息 （UNB6.1 和 UNB6.2 字段）。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息后，会将 UNB 标头升级到消息的上下文中。 如果不屏蔽，具有管理权限的任何人都可获取此上下文中的安全信息。 若要屏蔽此信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]替换信息的每个字符 **#** 字符。 这是一个单向过程：  **#** 字符无法转换为实际字符。  
  
6.  在**入站批处理选项**下拉列表中，执行以下操作：  
  
    1.  选择默认选项**将交换拆分为事务集-出错时暂停事务集**指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将仅挂起这些交换集。  
  
    2.  选择**将交换拆分为事务集-出错时暂停交换**指定 BizTalk Server 应分析每个事务集到单独的 XML 文档将交换中。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
    3.  选择**保留交换-出错时暂停交换**指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
    4.  选择**保留交换-出错时暂停事务集**指定 BizTalk Server，应保留交换不变，以创建 XML 文档是否为整个批处理的交换。 使用此选项时，如果交换中的一个或多个事务集未通过验证，BizTalk Server 将会挂起仅这些事务集，同时继续处理所有其他事务集。  
  
        > [!NOTE]
        >  如果你选择**保留交换-出错时暂停交换**或**保留交换-出错时暂停事务集**上的属性设置**ISA 段定义**和**GS 和 ST 段定义**页 （用于确定如何 BizTalk Server 将创建传出交换的 ISA，GS 和 ST 标头） 不适用于。 被保留的交换中存在的交换、组和事务集标头将在发送管道对其执行发送前的相关处理时予以保留。  
  
### <a name="to-configure-local-host--senders-settings"></a>配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (UNB5)**，输入的用于 BizTalk Server 中生成传出交换的交换控制编号的值的范围。 输入一个最小为 1、最大为 999999999 的数值。 此字段是必需字段。  
  
    > [!NOTE]
    >  第一个字段 (**UNB5.1**) 是前缀; 第二个和第三个字段 (**UNB5.2**) 包含要用作交换控制编号; 和第四个字段的数字范围 (**UNB5.3**)是的后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的；前缀和后缀保持不变。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
2.  有关**组控制编号 (UNG5)**、 输入前缀、 引用编号范围，以及 BizTalk Server 应该用于发送第一个交换组控制编号的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNG5.1**) 是前缀; 第二个和第三个字段 (**UNG5.2**) 包含要用于组控制编号; 和第四个字段的数字范围 (**UNG5.3**) 是的后缀。 前缀和后缀是可选的；控制编号是必需的。 每条新消息的控制编号是递增的直到达到最大值；前缀和后缀保持不变。 数字可以用在**UNG5.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限超出界限时**自动重置的最小值如果超出最大值。  
  
3.  有关**消息标头 （新罕布什尔大学）**，单击**应用新的 ID**、 输入前缀、 引用编号范围中，输入和输入 BizTalk 服务器应使用为事务集引用编号的后缀。  
  
    > [!NOTE]
    >  第一个字段 (**UNH1.1**) 是前缀; 第二个和第三个字段 (**UNH1.2**) 是引用编号范围; 和第四个字段 (**UNH1.3**) 是的后缀。 前缀和后缀是可选的；参考编号是必需的。 每条新消息的参考编号是递增的；前缀和后缀保持不变。 参考编号的默认值范围是 1 到 99999999999999。 数字可以用在**UNH1.2**。 控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。  
    >   
    >  若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限超出界限时**来将控制编号重置的最小值为，如果尚未超过最大值。  
  
4.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)