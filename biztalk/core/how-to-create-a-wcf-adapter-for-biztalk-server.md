---
title: "如何为 BizTalk Server 中创建的 WCF 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddaeb72-d263-4291-bd79-485fc736e6e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe1bbb9282db88f1b4370cea4b59ff4fcbfe6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-wcf-adapter-for-biztalk-server"></a><span data-ttu-id="00f83-102">如何为 BizTalk Server 创建 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="00f83-102">How to Create a WCF Adapter for BizTalk Server</span></span>
<span data-ttu-id="00f83-103">有三个部分创建 BizTalk[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="00f83-103">There are three parts to creating a BizTalk [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] adapter.</span></span>  
  
-   <span data-ttu-id="00f83-104">创建[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]Web 服务使用 BizTalk[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="00f83-104">Create a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard.</span></span> <span data-ttu-id="00f83-105">有关使用 BizTalk 信息[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]服务发布向导中，请参阅[发布 WCF 服务](../core/publishing-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="00f83-105">For information about using the BizTalk [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Publishing Wizard, see [Publishing WCF Services](../core/publishing-wcf-services.md).</span></span>  
  
-   <span data-ttu-id="00f83-106">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收和发送位置及端口。</span><span class="sxs-lookup"><span data-stu-id="00f83-106">Configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive and send locations and ports by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="00f83-107">有关如何执行此操作的示例，请参阅[如何配置接收和发送位置并 BAM WCF 侦听的端口](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)。</span><span class="sxs-lookup"><span data-stu-id="00f83-107">For an example of how to do this, see [How to Configure Receive and Send Locations and Ports for BAM WCF Interception](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md).</span></span>  
  
-   <span data-ttu-id="00f83-108">如果您是以 IIS 承载解决方案，则必须使用 IIS Manager 配置 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web 服务。</span><span class="sxs-lookup"><span data-stu-id="00f83-108">If you are hosting your solution in IIS, you must configure the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Web service by using IIS Manager.</span></span>  
  
    -   <span data-ttu-id="00f83-109">您必须对应用程序池用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="00f83-109">You must grant permissions to the App pool user.</span></span> <span data-ttu-id="00f83-110">若要执行此操作，请参阅[IIS 模拟的安全注意事项](../core/security-considerations-for-iis-impersonation.md)。</span><span class="sxs-lookup"><span data-stu-id="00f83-110">To do this, see [Security Considerations for IIS Impersonation](../core/security-considerations-for-iis-impersonation.md).</span></span>  
  
    -   <span data-ttu-id="00f83-111">您必须为应用程序设置目录安全性，如下面的过程所述。</span><span class="sxs-lookup"><span data-stu-id="00f83-111">You must set the directory security for your application as described in the following procedure.</span></span>  
  
## <a name="setting-the-directory-security"></a><span data-ttu-id="00f83-112">设置目录安全性</span><span class="sxs-lookup"><span data-stu-id="00f83-112">Setting the Directory Security</span></span>  
 <span data-ttu-id="00f83-113">请确保 [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] 服务的目录安全性访问控制允许匿名访问；这样可以简化应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="00f83-113">Ensure that the Directory Security Access Control for the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] service allows for anonymous access; this simplifies the application access.</span></span>  
  
 <span data-ttu-id="00f83-114">例如，如果你的应用程序名称为 MyBizTalkService3 并且必须是在默认网站 MyBizTalkService3，你可以按照此过程设置的访问控制。</span><span class="sxs-lookup"><span data-stu-id="00f83-114">For example, if your application is named MyBizTalkService3 and you have a MyBizTalkService3 that is in Default Websites, you would follow this procedure to set the access control.</span></span>  
  
#### <a name="to-set-the-access-control-in-windows-server-2008"></a><span data-ttu-id="00f83-115">在 Windows Server 2008 中设置访问控制</span><span class="sxs-lookup"><span data-stu-id="00f83-115">To set the access control in Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="00f83-116">单击**启动**，单击**所有程序**，展开**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="00f83-116">Click **Start**, click **All Programs**, expand **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="00f83-117">在 Internet 信息服务 (IIS) 管理器窗口中，展开你的服务器名称，展开**站点**，展开**Internet Information Services**，然后展开**Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="00f83-117">In the Internet Information Services (IIS) Manager window, expand your server name, expand **Sites**, expand **Internet Information Services**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="00f83-118">右键单击**MyBizTalkService3**，然后单击**编辑权限**。</span><span class="sxs-lookup"><span data-stu-id="00f83-118">Right-click **MyBizTalkService3**, and then click **Edit Permissions**.</span></span>  
  
4.  <span data-ttu-id="00f83-119">上**安全**选项卡**MyBizTalkService3 属性**对话框中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="00f83-119">On the **Security** tab of the **MyBizTalkService3 Properties** dialog box, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="00f83-120">在**权限 MyBizTalkService3**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="00f83-120">In the **Permissions for MyBizTalkService3** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="00f83-121">在**选择用户、 计算机或组**对话框中，键入`anonymous logon`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="00f83-121">In the **Select Users, Computers, or Groups** dialog box, type `anonymous logon` and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="00f83-122">选择**匿名登录**中**组或用户名**部分中，选择**读取 & 执行**中**匿名登录权限**部分，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="00f83-122">Select **ANONYMOUS LOGON** in the **Group or user names** section, select **Read & execute** in the **Permissions for ANONYMOUS LOGON** section, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="00f83-123">单击**确定**关闭**MyBizTalkService3 属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="00f83-123">Click **OK** to close the **MyBizTalkService3 Properties** dialog box.</span></span>  
  
 <span data-ttu-id="00f83-124">要确认该服务配置正确，请右键单击该服务，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="00f83-124">To confirm that the service is configured correctly, right-click the service, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="00f83-125">如果正确配置了该服务，您将看到一个类似于如下的屏幕。</span><span class="sxs-lookup"><span data-stu-id="00f83-125">If the service is configured correctly, you will see a screen similar to the one below.</span></span>  
  
 <span data-ttu-id="00f83-126">![BizTalkServiceInstance 服务屏幕](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span><span class="sxs-lookup"><span data-stu-id="00f83-126">![BizTalkServiceInstance Service Screen](../core/media/ff0e4ba0-59e7-47d9-a252-2859179f5645.gif "ff0e4ba0-59e7-47d9-a252-2859179f5645")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f83-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00f83-127">See Also</span></span>  
 [<span data-ttu-id="00f83-128">配置 WCF 适配器以截获 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="00f83-128">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)