---
title: 配置本地主机设置 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c66c1e63-c654-4ccb-b424-34c06f1ce94e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca40e971b4c19af1490fa320fc2eb303640a438b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006054"
---
# <a name="configuring-local-host-settings-x12-interchange-settings"></a>配置本地主机设置（X12-交换设置）
本地主机设置控制如何处理 EDI 交换。 此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。 在接收方的设置中，可以指定传入的批是拆分为事务集还是保留。 如果保留，可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在发生错误时是否挂起交换或事务集。 在发送方的设置中，您可以指定如何为传出消息生成控制编号。  
  
> [!NOTE]
>  此处所述的设置同样适用于 HIPAA 交换。  
> 
> [!IMPORTANT]
>  以下属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果你清除了**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**参与方 a 的复选框  
> 
> - 下的所有属性**发件人的设置**部分。  
> 
>   以下属性中的相同页上将禁用与此类似，**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
> 
> - 下的所有属性**接收方设置**部分。  
  
## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-local-host--receivers-settings"></a>配置本地主机 – 接收方设置  
  
1. 创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2. 在单向协议选项卡下**交换设置**部分中，单击**本地主机设置**。  
  
3. 清除**将确认路由到发送管道请求-响应接收端口**返回由单独的确认的发送端口。 如果将该属性保留为选中状态，则会在与双向请求-响应接收端口关联的发送端口上返回确认。  
  
4. 若要指定确认中使用的事务集控制编号范围，请输入中的值**确认控制编号 (ST02)** 字段。 请在中间两个字段中输入一个数值，而为前缀和后缀字段输入字母数字值（如果需要）。 中间字段是必填字段，包含控制编号的最小值和最大值；前缀和后缀可选。 所有三个字段的最大长度均为 9 个字符。  
  
    若要重置当前事务集控制编号的最小值，请单击**重置**。 检查**重置为下限值超出界限时**重置为下限的控制编号，一旦超出了最大值。  
  
5. 选择**屏蔽上下文属性中的安全/授权/密码信息**复选框以启用屏蔽上下文属性以防止信息中的授权/密码安全信息 （ISA2 和 ISA4 字段）泄露。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息时，它将 ISA 标头升级到消息的上下文中。 如果不屏蔽，具有管理权限的任何人都可获取此上下文中的安全信息。 为了屏蔽此信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]替代信息中的每个字符**#** 字符。 这是一个单向过程： **#** 字符不能转换为实际的字符。  
  
6. 在中**入站批处理选项**下拉列表中，执行以下操作：  
  
   1.  选择默认选项**将交换拆分为事务集-出错时挂起事务集**以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将仅挂起这些交换集。  
  
   2.  选择**将交换拆分为事务集-出错时挂起交换**以指定 BizTalk Server 应解析为单独 XML 文档将交换中设置每个事务。 然后，BizTalk Server 将相应的信封应用到事务集，并且将事务集文档路由至 MessageBox。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
   3.  选择**保留交换-出错时挂起交换**以指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 选择此选项后，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起整个交换。  
  
   4.  选择**保留交换-出错时挂起事务集**以指定 BizTalk Server 应原样保留交换不变，同时创建一个 XML 文档为整个批处理交换。 使用此选项，如果交换中的一个或多个事务集未能通过验证，BizTalk Server 将挂起的事务集，同时继续处理所有其他事务集。  
  
       > [!NOTE]
       >  如果选择**保留交换-出错时挂起交换**或**保留交换-出错时挂起事务集**，交换、 组和事务集段属性 (确定 BizTalk Server 将如何创建传出交换的 ISA、 GS 和 ST 标头） 不适用。 被保留的交换中存在的交换、组和事务集标头将在发送管道对其执行发送前的相关处理时予以保留。  
  
### <a name="to-configure-local-host--senders-settings"></a>配置本地主机 – 发送方设置  
  
1.  有关**交换控制编号 (ISA13)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。 输入一个最小为 1、最大为 999999999 的数值。 此字段是必需字段。  
  
     若要将控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
2.  有关**组控制编号 (GS06)**，输入 BizTalk Server 应为组控制编号使用的数字范围。 输入一个最小为 1 个字符最大为 9 个字符的数值。 这是必填字段。  
  
     若要将组控制编号重置为指定的最小值，请单击**重置**按钮。 检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。  
  
3.  有关**事务集控制编号 (ST02)**，单击**应用新 ID**然后为可选前缀和后缀输入所需的中间字段的数值和字母数字值的范围。 所有四个字段的最大长度为 9 个字符。  
  
     若要重置当前事务集控制编号的最小值，请单击**重置**。 选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。  
  
4.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (X12)](../core/configuring-interchange-settings-x12.md)