---
title: "配置警报队列选项和通知 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914af88b989c73444e16acedf43b9a236897859d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-alert-queue-options-and-notifications"></a><span data-ttu-id="a0c1e-102">配置警报队列选项和通知</span><span class="sxs-lookup"><span data-stu-id="a0c1e-102">Configuring Alert Queue Options and Notifications</span></span>
<span data-ttu-id="a0c1e-103">ESB 管理门户使用 ESB 警报服务来生成警报，如错误消息到达门户中，并使用 ESB 通知服务进行排队，并将警报通知发送到订阅警报的用户。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-103">The ESB Management Portal uses the ESB Alert Service to generate alerts as fault messages arrive at the portal, and it uses the ESB Notification Service to queue and send alert notifications to users that subscribe to alerts.</span></span> <span data-ttu-id="a0c1e-104">你可以编辑这些服务在 ESB 管理门户中使用的设置。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-104">You can edit the settings used by these services in the ESB Management Portal.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a><span data-ttu-id="a0c1e-105">若要配置 ESB 警报服务的设置</span><span class="sxs-lookup"><span data-stu-id="a0c1e-105">To configure the settings for the ESB Alert Service</span></span>  
  
1.  <span data-ttu-id="a0c1e-106">确保您登录到门户使用的是 Microsoft BizTalk Server 管理员帐户 （其中门户管理员自动成员身份组） 的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-106">Ensure that you log on to the portal using an account that is a member of the Microsoft BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="a0c1e-107">指向**管理员**在门户的主菜单上，选项卡，然后单击**错误设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-107">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="a0c1e-108">在**警报队列选项**部分，选中或清除**启用警报队列服务**复选框以启用或禁用服务。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-108">In the **Alert Queue Options** section, select or clear the **Enable Alert Queue Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="a0c1e-109">如果你启用该服务，编辑中的其余的控件，以满足我们的要求的值。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-109">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="a0c1e-110">服务与 Microsoft Active Directory 交互，因此你必须指定相应的 LDAP （轻型目录访问协议） 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-110">The service interacts with Microsoft Active Directory, so you must specify the appropriate LDAP (Lightweight Directory Access Protocol) connection string.</span></span> <span data-ttu-id="a0c1e-111">你还可以指定的队列批大小和轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-111">You can also specify the queue batch size and polling interval.</span></span>  
  
5.  <span data-ttu-id="a0c1e-112">单击**保存**以保存新的设置。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-112">Click **Save** to save the new settings.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a><span data-ttu-id="a0c1e-113">若要配置 ESB 警报的电子邮件通知服务的设置</span><span class="sxs-lookup"><span data-stu-id="a0c1e-113">To configure the settings for the ESB Alert Email Notification service</span></span>  
  
1.  <span data-ttu-id="a0c1e-114">确保您登录到门户使用的 BizTalk Server 管理员帐户 （其中门户管理员自动成员身份组） 成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-114">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="a0c1e-115">指向**管理员**在门户的主菜单上，选项卡，然后单击**错误设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-115">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="a0c1e-116">在**警报的电子邮件选项**部分，选中或清除**启用警报电子邮件服务**复选框以启用或禁用服务。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-116">In the **Alert Email Options** section, select or clear the **Enable Alert Email Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="a0c1e-117">如果你启用该服务，编辑中的其余的控件，以满足我们的要求的值。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-117">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="a0c1e-118">指定电子邮件服务器名称和"发件人"地址、 更改轮询间隔和批处理大小根据需要，并指定服务使用的可扩展样式表语言转换 (XSLT) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-118">Specify the e-mail server name and the "from" address, change the polling interval and batch size as required, and specify the path to Extensible Stylesheet Language Transformations (XSLT) files that the service uses.</span></span>  
  
5.  <span data-ttu-id="a0c1e-119">单击**保存**以保存新的设置。</span><span class="sxs-lookup"><span data-stu-id="a0c1e-119">Click **Save** to save the new settings.</span></span>