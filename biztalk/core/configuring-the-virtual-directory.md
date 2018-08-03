---
title: 配置虚拟目录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd87b89c6c23e709f21e78e3ea98dd2b84575ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968811"
---
# <a name="configuring-the-virtual-directory"></a><span data-ttu-id="f3cdc-102">配置虚拟目录</span><span class="sxs-lookup"><span data-stu-id="f3cdc-102">Configuring the Virtual Directory</span></span>
<span data-ttu-id="f3cdc-103">本主题演示了为用户配置虚拟目录并验证应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-103">This topic shows the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
## <a name="configuring-the-directory"></a><span data-ttu-id="f3cdc-104">配置目录</span><span class="sxs-lookup"><span data-stu-id="f3cdc-104">Configuring the Directory</span></span>  
  
#### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="f3cdc-105">若要配置的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="f3cdc-105">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="f3cdc-106">在 %systemdrive% 上，创建一个将配置为虚拟目录的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-106">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="f3cdc-107">单击**启动**，指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-107">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="f3cdc-108">展开**\<服务器名称\>** 然后展开**站点**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-108">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="f3cdc-109">右键单击**Default Web Site**单击**添加虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-109">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="f3cdc-110">在**添加虚拟目录**对话框框中，键入别名。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-110">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="f3cdc-111">键入在步骤 1 中创建的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-111">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="f3cdc-112">或者，单击 **（...）** 以浏览到文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-112">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="f3cdc-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-113">Click **OK**.</span></span> <span data-ttu-id="f3cdc-114">该文件夹将显示下**Default Web Site**文件夹。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-114">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="f3cdc-115">右键单击文件夹，然后单击**转换为应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-115">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="f3cdc-116">在**添加应用程序**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-116">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="f3cdc-117">该文件夹将转换为应用程序（您可以看到图标的变化 – 从文件夹图标变为网站图标）。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-117">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="verifying-an-application-for-a-user"></a><span data-ttu-id="f3cdc-118">为用户验证应用程序</span><span class="sxs-lookup"><span data-stu-id="f3cdc-118">Verifying an Application for a User</span></span>  
 <span data-ttu-id="f3cdc-119">Internet 信息服务 (IIS) 应用程序在高度隔离的环境中运行；因此，必须使用以下过程验证应用程序是否可以在 BizTalk Server 独立主机用户组中的用户上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-119">Internet Information Services (IIS) applications run in high isolation; therefore, you must verify that the application can run in the context of a user in the BizTalk Server Isolated Host Users group by using the following procedure.</span></span>  
  
#### <a name="to-verify-an-application-for-a-user"></a><span data-ttu-id="f3cdc-120">若要验证用于用户的应用程序</span><span class="sxs-lookup"><span data-stu-id="f3cdc-120">To verify an application for a user</span></span>  
  
1.  <span data-ttu-id="f3cdc-121">在 Control Panel 中，打开**管理工具**，然后单击**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-121">In Control Panel, open **Administrative Tools**, and then click **Component Services**.</span></span>  
  
2.  <span data-ttu-id="f3cdc-122">导航到中的 COM + 应用程序**组件服务**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-122">Navigate to the COM+ application in **Component Services**.</span></span>  
  
3.  <span data-ttu-id="f3cdc-123">右键单击的 COM + 应用程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-123">Right-click the COM+ application, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f3cdc-124">单击**标识**和更改此 COM + 应用程序是 BizTalk Server 组的成员的用户在其下运行的标识。</span><span class="sxs-lookup"><span data-stu-id="f3cdc-124">Click **Identify** and change the identity under which this COM+ application runs to a user that is a member of a BizTalk Server group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3cdc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3cdc-125">See Also</span></span>  
 [<span data-ttu-id="f3cdc-126">适配器中的安全</span><span class="sxs-lookup"><span data-stu-id="f3cdc-126">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)