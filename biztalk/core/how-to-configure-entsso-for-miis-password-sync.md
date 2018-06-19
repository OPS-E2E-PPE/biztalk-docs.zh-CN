---
title: 如何为 miis 进行密码同步配置 ENTSSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89438935-37c1-4ac9-9ca2-7af8d9bfd3ae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1587c2e3c0d2164a7ffd3842b3d74df5b04685
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248941"
---
# <a name="how-to-configure-entsso-for-miis-password-sync"></a><span data-ttu-id="f8dd1-102">如何配置 ENTSSO 以实现 MIIS 密码同步</span><span class="sxs-lookup"><span data-stu-id="f8dd1-102">How to Configure ENTSSO for MIIS Password Sync</span></span>
<span data-ttu-id="f8dd1-103">配置完 XML 文件和 Microsoft Identity Integration Server (MIIS) 后，其余配置步骤可在企业单一登录 (ENTSSO) 系统中进行。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-103">After configuring the XML file and Microsoft Identity Integration Server (MIIS), the remaining configuration steps take place in the Enterprise Single Sign-On (ENTSSO) system.</span></span>  
  
### <a name="to-allow-password-sync-from-miis"></a><span data-ttu-id="f8dd1-104">从 MIIS 实现密码同步</span><span class="sxs-lookup"><span data-stu-id="f8dd1-104">To allow Password Sync from MIIS</span></span>  
  
1.  <span data-ttu-id="f8dd1-105">在 Enterprise 上单一登录，单击**服务器**节点。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-105">In Enterprise Single Sign-On, click the **Servers** node.</span></span>  
  
2.  <span data-ttu-id="f8dd1-106">右键单击适当的服务器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-106">Right-click the appropriate server, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f8dd1-107">单击**密码同步**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-107">Click the **Password Sync** tab.</span></span>  
  
4.  <span data-ttu-id="f8dd1-108">选择**允许从 miis 进行密码同步**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-108">Select **Allow password sync from MIIS**.</span></span>  
  
5.  <span data-ttu-id="f8dd1-109">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-109">Click **OK**.</span></span>  
  
### <a name="to-enable-password-sync-on-the-system-level"></a><span data-ttu-id="f8dd1-110">启用系统级别的密码同步</span><span class="sxs-lookup"><span data-stu-id="f8dd1-110">To enable Password Sync on the system level</span></span>  
  
1.  <span data-ttu-id="f8dd1-111">在 Enterprise 上单一登录，右键单击**系统**节点。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-111">In Enterprise Single Sign-On, right-click the **System** node.</span></span>  
  
2.  <span data-ttu-id="f8dd1-112">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-112">Click **Properties**.</span></span>  
  
     <span data-ttu-id="f8dd1-113">**属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-113">The **Properties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="f8dd1-114">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-114">Click the **Options** tab.</span></span>  
  
4.  <span data-ttu-id="f8dd1-115">在**启用密码同步**字段中，选择**从 Windows 到适配器**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-115">In the **Enable Password Sync** field, select **From Windows to Adapters**.</span></span>  
  
     <span data-ttu-id="f8dd1-116">**其他配置**</span><span class="sxs-lookup"><span data-stu-id="f8dd1-116">**Additional Configuration**</span></span>  
  
     <span data-ttu-id="f8dd1-117">最后，您必须配置以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="f8dd1-117">Finally, you must configure one of the following:</span></span>  
  
    -   <span data-ttu-id="f8dd1-118">接受 Windows 密码同步的密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-118">A Password Sync Adapter that accepts Windows Password Sync.</span></span>  
  
    -   <span data-ttu-id="f8dd1-119">至少对一个应用程序启用直接密码同步。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-119">Direct Password Sync enabled on at least one application.</span></span>  
  
     <span data-ttu-id="f8dd1-120">有关如何进行此操作的信息，请参阅“密码同步”文档。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-120">For information about how to do this, refer to your Password Sync documentation.</span></span>  
  
### <a name="to-configure-the-entsso-ma-for-miis-password-sync"></a><span data-ttu-id="f8dd1-121">配置 EntSSO MA 以实现 MIIS 密码同步</span><span class="sxs-lookup"><span data-stu-id="f8dd1-121">To configure the EntSSO MA for MIIS Password Sync</span></span>  
  
1.  <span data-ttu-id="f8dd1-122">ENTSSO 管理代理上**属性**页上，单击**配置扩展**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-122">On the ENTSSO Management Agent **Properties** page, click **Configure Extensions**.</span></span>  
  
2.  <span data-ttu-id="f8dd1-123">在**密码扩展的连接信息**字段中，单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-123">In the **Connection information for password extension** field, click **Settings**.</span></span>  
  
3.  <span data-ttu-id="f8dd1-124">在**连接到**字段中，输入将接收密码更改的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-124">In the **Connect To** field enter the name of the computer that will receive the password changes.</span></span>  
  
     <span data-ttu-id="f8dd1-125">该计算机名必须采用为该域上的 ENTSSO 服务创建服务主体名称 (SPN) 时所使用的同一格式。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-125">The computer name must be in the same format that was used when creating the Service Principal Name (SPN) for the ENTSSO service on the domain.</span></span>  
  
     <span data-ttu-id="f8dd1-126">例如：</span><span class="sxs-lookup"><span data-stu-id="f8dd1-126">For example:</span></span>  
  
     <span data-ttu-id="f8dd1-127">使用短格式 - SPN = ENTSSO/ABCD1411，则输入 ABCD1411</span><span class="sxs-lookup"><span data-stu-id="f8dd1-127">Short format - SPN = ENTSSO/ABCD1411, then enter ABCD1411</span></span>  
  
4.  <span data-ttu-id="f8dd1-128">使用长格式 - SPN = ENTSSO/ABCD1411.CompanyName.com，则输入 ABCD1411.CompanyName.com</span><span class="sxs-lookup"><span data-stu-id="f8dd1-128">Long format - SPN = ENTSSO/ABCD1411.CompanyName.com then enter ABCD1411.CompanyName.com</span></span>  
  
### <a name="additional-configuration-steps"></a><span data-ttu-id="f8dd1-129">其他配置步骤</span><span class="sxs-lookup"><span data-stu-id="f8dd1-129">Additional Configuration Steps</span></span>  
  
1.  <span data-ttu-id="f8dd1-130">单击**启动**，指向**所有程序**，指向**Microsoft Identity Integration Server**，然后单击**Identity Manager**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-130">Click **Start**, point to **All Programs**, point to **Microsoft Identity Integration Server**, and then click **Identity Manager**.</span></span>  
  
2.  <span data-ttu-id="f8dd1-131">在“工具”  菜单上，单击“选项” 。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-131">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="f8dd1-132">选择**启用密码同步**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-132">Select **Enable Password Synchronization**.</span></span>  
  
4.  <span data-ttu-id="f8dd1-133">在**管理代理查看**，选择**ADMA**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-133">In the **Management Agents view**, select **ADMA**.</span></span>  
  
5.  <span data-ttu-id="f8dd1-134">在**操作**窗格中，选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-134">In the **Action** pane, select **Properties**.</span></span>  
  
6.  <span data-ttu-id="f8dd1-135">上**属性**页上，选择**配置目录分区**，然后选择**启用密码同步源作为此分区**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-135">On the **Properties** page, select **Configure Directory Partitions**, and then select **Enable this partition as a password synchronization source**.</span></span>  
  
7.  <span data-ttu-id="f8dd1-136">单击**目标**，然后选择 ENTSSOMA2 以使其能够接收从 miis 进行密码更改。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-136">Click **Targets**, and then select ENTSSOMA2 to enable it to receive password changes from MIIS.</span></span> <span data-ttu-id="f8dd1-137">取消选择 ENTSSOMA。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-137">Deselect ENTSSOMA.</span></span> <span data-ttu-id="f8dd1-138">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-138">Click **OK**, and then click **OK** again.</span></span>  
  
8.  <span data-ttu-id="f8dd1-139">在**管理代理**视图中，选择**ENTSSOMA2**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-139">In the **Management Agent** view, select **ENTSSOMA2**.</span></span> <span data-ttu-id="f8dd1-140">在右侧窗格中，选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-140">In the right-hand pane, select **Properties**.</span></span> <span data-ttu-id="f8dd1-141">上**属性**页上，单击**配置扩展**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-141">On the **Properties** page, click **Configure Extensions**.</span></span>  
  
9. <span data-ttu-id="f8dd1-142">确认**启用密码管理**已选择，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-142">Confirm that **Enable password management** is selected, and then click **Settings**.</span></span>  
  
10. <span data-ttu-id="f8dd1-143">在**连接设置**对话框中，指定下列各项：</span><span class="sxs-lookup"><span data-stu-id="f8dd1-143">In the **Connection Settings** dialog, specify the following:</span></span>  
  
    -   <span data-ttu-id="f8dd1-144">连接到： INTSVR1.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f8dd1-144">Connect To: INTSVR1.fabrikam.com</span></span>  
  
    -   <span data-ttu-id="f8dd1-145">用户： fabrikam\ssosvcact</span><span class="sxs-lookup"><span data-stu-id="f8dd1-145">User: fabrikam\ssosvcact</span></span>  
  
    -   <span data-ttu-id="f8dd1-146">密码： ssosvcact</span><span class="sxs-lookup"><span data-stu-id="f8dd1-146">Password: ssosvcact</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f8dd1-147">该帐户应与在 INTSVR1.fabrikam.com 上配置的 ENTSSO 服务帐户相匹配。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-147">This account should match the ENTSSO service account configured on INTSVR1.fabrikam.com.</span></span>  
  
11. <span data-ttu-id="f8dd1-148">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-148">Click **OK**, and then click **OK** again.</span></span>  
  
12. <span data-ttu-id="f8dd1-149">您也可以禁用 MIIS 的密码同步。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-149">You can also disable password sync for MIIS.</span></span> <span data-ttu-id="f8dd1-150">为此，请在**Identity Manager**，单击**工具**菜单上，单击**选项**，然后取消选中**启用密码同步**。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-150">To do this, in **Identity Manager**, click the **Tools** menu, click **Options**, and then deselect **Enable Password Synchronization**.</span></span>  
  
     <span data-ttu-id="f8dd1-151">将应用下列限制：</span><span class="sxs-lookup"><span data-stu-id="f8dd1-151">The following restrictions will apply:</span></span>  
  
    -   <span data-ttu-id="f8dd1-152">为使“密码同步”功能可以正常工作，必须在作为 ENTSSO 管理代理通信对象的 ENTSSO 服务帐户上对 SPN 进行配置。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-152">For Password Sync to function properly, SPN must be configured on the ENTSSO service account that the ENTSSO Management Agent will communicate with.</span></span>  
  
    -   <span data-ttu-id="f8dd1-153">MIIS 和 ENTSSO 服务器之间的通信需要 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-153">Communication between MIIS and the ENTSSO server requires Kerberos.</span></span>  
  
13. <span data-ttu-id="f8dd1-154">在 ENTSSO 管理代理的 MIIS 连接配置中配置“密码扩展”时，指定帐户必须与将从 MIIS 接收密码的 ENTSSO 服务器的服务帐户相匹配。</span><span class="sxs-lookup"><span data-stu-id="f8dd1-154">When configuring Password Extension in the MIIS connection configuration for the ENTSSO Management Agent, the account specified must match the service account for the ENTSSO server that will receive passwords from MIIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8dd1-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8dd1-155">See Also</span></span>  
 [<span data-ttu-id="f8dd1-156">如何使用 ENTSSO 管理代理</span><span class="sxs-lookup"><span data-stu-id="f8dd1-156">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)