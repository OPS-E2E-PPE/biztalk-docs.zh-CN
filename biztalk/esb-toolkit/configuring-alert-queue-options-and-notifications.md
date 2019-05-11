---
title: 配置警报队列选项和通知 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f78afbf9-6e27-4887-8424-f265fbd8448a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0938ceed9adcf117bcc54433eff1e9d7cd06ab8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302123"
---
# <a name="configuring-alert-queue-options-and-notifications"></a><span data-ttu-id="c0323-102">配置警报队列选项和通知</span><span class="sxs-lookup"><span data-stu-id="c0323-102">Configuring Alert Queue Options and Notifications</span></span>
<span data-ttu-id="c0323-103">ESB 管理门户使用 ESB 警报服务生成警报，如错误消息到达时在门户中，并使用 ESB 通知服务进行排队，并将警报通知发送到订阅警报的用户。</span><span class="sxs-lookup"><span data-stu-id="c0323-103">The ESB Management Portal uses the ESB Alert Service to generate alerts as fault messages arrive at the portal, and it uses the ESB Notification Service to queue and send alert notifications to users that subscribe to alerts.</span></span> <span data-ttu-id="c0323-104">可以编辑使用 ESB 管理门户中的这些服务的设置。</span><span class="sxs-lookup"><span data-stu-id="c0323-104">You can edit the settings used by these services in the ESB Management Portal.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-service"></a><span data-ttu-id="c0323-105">若要配置 ESB 警报服务的设置</span><span class="sxs-lookup"><span data-stu-id="c0323-105">To configure the settings for the ESB Alert Service</span></span>  
  
1.  <span data-ttu-id="c0323-106">请确保您登录到在门户中使用该帐户是 （门户管理员的自动成员） 的 Microsoft BizTalk Server Administrators 帐户组的成员。</span><span class="sxs-lookup"><span data-stu-id="c0323-106">Ensure that you log on to the portal using an account that is a member of the Microsoft BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="c0323-107">指向**管理员**在门户的主菜单上，选项卡，然后单击**容错设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c0323-107">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="c0323-108">在中**警报队列选项**部分中，选择或清除**启用警报队列服务**复选框以启用或禁用服务。</span><span class="sxs-lookup"><span data-stu-id="c0323-108">In the **Alert Queue Options** section, select or clear the **Enable Alert Queue Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="c0323-109">如果启用该服务，编辑以满足我们的要求的其余控件中的值。</span><span class="sxs-lookup"><span data-stu-id="c0323-109">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="c0323-110">该服务与 Microsoft Active Directory 交互，因此你必须指定相应的 LDAP （轻型目录访问协议） 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="c0323-110">The service interacts with Microsoft Active Directory, so you must specify the appropriate LDAP (Lightweight Directory Access Protocol) connection string.</span></span> <span data-ttu-id="c0323-111">此外可以指定队列批大小和轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="c0323-111">You can also specify the queue batch size and polling interval.</span></span>  
  
5.  <span data-ttu-id="c0323-112">单击**保存**以保存新设置。</span><span class="sxs-lookup"><span data-stu-id="c0323-112">Click **Save** to save the new settings.</span></span>  
  
### <a name="to-configure-the-settings-for-the-esb-alert-email-notification-service"></a><span data-ttu-id="c0323-113">若要配置 ESB 警报电子邮件通知服务的设置</span><span class="sxs-lookup"><span data-stu-id="c0323-113">To configure the settings for the ESB Alert Email Notification service</span></span>  
  
1.  <span data-ttu-id="c0323-114">请确保您登录到在门户中使用该帐户是 （门户管理员的自动成员） 的 BizTalk Server Administrators 帐户组的成员。</span><span class="sxs-lookup"><span data-stu-id="c0323-114">Ensure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group (of which portal administrators are automatically a member).</span></span>  
  
2.  <span data-ttu-id="c0323-115">指向**管理员**在门户的主菜单上，选项卡，然后单击**容错设置**以打开门户[错误设置页](../esb-toolkit/fault-settings-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c0323-115">Point to the **Admin** tab on the portal main menu, and then click **Fault Settings** to open the portal [Fault Settings Page](../esb-toolkit/fault-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="c0323-116">在中**警报的电子邮件选项**部分中，选择或清除**启用警报电子邮件服务**复选框以启用或禁用服务。</span><span class="sxs-lookup"><span data-stu-id="c0323-116">In the **Alert Email Options** section, select or clear the **Enable Alert Email Service** check box to enable or disable the service.</span></span>  
  
4.  <span data-ttu-id="c0323-117">如果启用该服务，编辑以满足我们的要求的其余控件中的值。</span><span class="sxs-lookup"><span data-stu-id="c0323-117">If you enable the service, edit the values in the remaining controls to suit our requirements.</span></span> <span data-ttu-id="c0323-118">指定电子邮件服务器名称和"发件人"地址、 更改轮询间隔和批大小为必需的并指定该服务使用的可扩展样式表语言转换 (XSLT) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c0323-118">Specify the e-mail server name and the "from" address, change the polling interval and batch size as required, and specify the path to Extensible Stylesheet Language Transformations (XSLT) files that the service uses.</span></span>  
  
5.  <span data-ttu-id="c0323-119">单击**保存**以保存新设置。</span><span class="sxs-lookup"><span data-stu-id="c0323-119">Click **Save** to save the new settings.</span></span>