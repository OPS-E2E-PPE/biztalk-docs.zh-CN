---
title: 安装适用于 SAP 的数据提供程序的自定义 Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, custom RFCs for the Data Provider for SAP
- installing, custom RFCs for the Data Provider for SAP
- installing custom RFCs, how to
ms.assetid: 7a99db70-fa5a-4c04-9dc7-b71613d4364e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f94bb4b6a6f094211654f5c3c0964bbf84d42f56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989590"
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a><span data-ttu-id="2385b-102">安装适用于 SAP 的数据提供程序的自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="2385b-102">Install Custom RFCs for the Data Provider for SAP</span></span>
<span data-ttu-id="2385b-103">如果你想要使用用于 mySAP Business Suite 的.NET Framework 数据提供程序来访问 SAP 系统，安装自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="2385b-103">Install the custom RFCs if you want to use the .NET Framework Data Provider for mySAP Business Suite to access the SAP system.</span></span>

<span data-ttu-id="2385b-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要执行某些操作到 SAP 系统上的自定义 Rfc:</span><span class="sxs-lookup"><span data-stu-id="2385b-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires custom RFCs to perform some operations on the SAP system to:</span></span>
  
- <span data-ttu-id="2385b-105">运行选择的操作，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXTRACT_DATA_OO RFC。</span><span class="sxs-lookup"><span data-stu-id="2385b-105">Run the SELECT operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXTRACT_DATA_OO RFC.</span></span>  
  
- <span data-ttu-id="2385b-106">运行 EXECQUERY 操作[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXECUTE_SAP_QUERY RFC。</span><span class="sxs-lookup"><span data-stu-id="2385b-106">Run the EXECQUERY operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
<span data-ttu-id="2385b-107">若要执行这些操作上的 SAP 系统，必须在 SAP 系统上安装这些自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="2385b-107">To perform these operations on the SAP system, you must install these custom RFCs on the SAP system.</span></span> <span data-ttu-id="2385b-108">如果您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，安装程序将复制的 RFC 传输[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]为压缩文件 (customRFC.zip) 系统上安装适配器。</span><span class="sxs-lookup"><span data-stu-id="2385b-108">If you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the Setup program copies the RFC transport for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as a compressed file (customRFC.zip) on the system where you install the adapter.</span></span> <span data-ttu-id="2385b-109">Zip 文件通常安装在*\<安装驱动器\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft.NET Framework 数据提供程序用于 mySAP Business Suite*。</span><span class="sxs-lookup"><span data-stu-id="2385b-109">The zip file is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*.</span></span> 
  
 <span data-ttu-id="2385b-110">提取 zip 文件后, 您将找到四个数据文件、 两个以下命名模式 K9 *。BI1 （例如，类似于 K900534。BI1)，和其他两种模式 R9\*。BI1 （例如，类似于 R900534。BI1)。</span><span class="sxs-lookup"><span data-stu-id="2385b-110">After extracting the zip file, you will find four data files, two following the naming pattern K9*.BI1 (for example, similar to K900534.BI1), and the other two following the pattern R9\*.BI1 (for example, similar to R900534.BI1).</span></span>  
  

  
1. <span data-ttu-id="2385b-111">将提取的文件复制到 SAP 应用程序服务器运行适配器的计算机。</span><span class="sxs-lookup"><span data-stu-id="2385b-111">Copy the extracted files from the computer running the adapters to the SAP application server.</span></span>  
  
   1.  <span data-ttu-id="2385b-112">以 SAP R/3 系统管理员，以在开发系统的 SAP 应用程序服务器登录。</span><span class="sxs-lookup"><span data-stu-id="2385b-112">Log in as the SAP R/3 system administrator to the SAP application server of your development system.</span></span>  
  
   2.  <span data-ttu-id="2385b-113">复制使用的命名模式 K9 \* 的两个传输文件。从 SAP 应用程序服务器上的以下目录中运行适配器的计算机上安装目录 BI1:</span><span class="sxs-lookup"><span data-stu-id="2385b-113">Copy the two transport files with the naming pattern K9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\cofiles`  
  
   3.  <span data-ttu-id="2385b-114">复制使用的命名模式 R9 \* 的两个传输文件。从 SAP 应用程序服务器上的以下目录中运行适配器的计算机上安装目录 BI1:</span><span class="sxs-lookup"><span data-stu-id="2385b-114">Copy the two transport files with the naming pattern R9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\data`  
  
2. <span data-ttu-id="2385b-115">加载到 SAP 应用程序服务器上的传输缓冲区的传输。</span><span class="sxs-lookup"><span data-stu-id="2385b-115">Load the transport into the transport buffer on the SAP application server.</span></span>  
  
   1.  <span data-ttu-id="2385b-116">在命令提示符处，导航到 SAP 应用程序服务器上的传输程序目录：</span><span class="sxs-lookup"><span data-stu-id="2385b-116">At the command prompt, navigate to the transport program directory on the SAP application server:</span></span>  
  
        `<drive>:\usr\sap\trans\bin`  
  
   2.  <span data-ttu-id="2385b-117">若要加载到传输缓冲区的传输，执行以下命令，`\usr\sap\trans\bin`目录并替换*sysid*与在开发系统的系统 ID:</span><span class="sxs-lookup"><span data-stu-id="2385b-117">To load the transport into the transport buffer, execute the following command at the `\usr\sap\trans\bin` directory and replace *sysid* with the system ID of your development system:</span></span>  
  
       ```  
       tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        <span data-ttu-id="2385b-118">其中， *TransportNumber*是实际传输数字 (例如 BI1K900534)。</span><span class="sxs-lookup"><span data-stu-id="2385b-118">where, *TransportNumber* is the actual transport number (for example BI1K900534).</span></span>  
  
   3.  <span data-ttu-id="2385b-119">之后`tp`命令完成，你将看到类似于以下报表：</span><span class="sxs-lookup"><span data-stu-id="2385b-119">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       Addtobuffer successful for TransportNumber  
       tp finished with return code: 0  
       ```  
  
        <span data-ttu-id="2385b-120">返回代码"0"表示操作成功。</span><span class="sxs-lookup"><span data-stu-id="2385b-120">Return code "0" means that the operation succeeded.</span></span>  
  
        <span data-ttu-id="2385b-121">返回代码为 0 或 4 是可接受的。</span><span class="sxs-lookup"><span data-stu-id="2385b-121">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="2385b-122">如果收到返回代码为 8 或更高版本，请与 Microsoft 客户服务和支持联系。</span><span class="sxs-lookup"><span data-stu-id="2385b-122">Contact Microsoft Customer Service and Support, if you receive a return code of 8 or above.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="2385b-123">传输文件的第二个集，请重复步骤 (b) 和 (c)。</span><span class="sxs-lookup"><span data-stu-id="2385b-123">Repeat steps (b) and (c) for the second set of transport files.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="2385b-124">您可以轻松地实际传输数派生 cofile 文件名称。</span><span class="sxs-lookup"><span data-stu-id="2385b-124">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="2385b-125">例如，名为 K900534 cofile。BI1 提供 BI1K900534 传输数。</span><span class="sxs-lookup"><span data-stu-id="2385b-125">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
3. <span data-ttu-id="2385b-126">导入 SAP 传输。</span><span class="sxs-lookup"><span data-stu-id="2385b-126">Import the transport into SAP.</span></span>  
  
   1.  <span data-ttu-id="2385b-127">执行以下命令在命令提示符：</span><span class="sxs-lookup"><span data-stu-id="2385b-127">Execute the following command at the command prompt:</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
       ```  
  
        <span data-ttu-id="2385b-128">替换*sysid*与在开发系统的系统 ID。</span><span class="sxs-lookup"><span data-stu-id="2385b-128">Replace *sysid* with the system ID of your development system.</span></span> <span data-ttu-id="2385b-129">替换*clientnumber*开发系统的客户端数。</span><span class="sxs-lookup"><span data-stu-id="2385b-129">Replace *clientnumber* with the client number of your development system.</span></span>  
  
        <span data-ttu-id="2385b-130">U2 参数可用于覆盖以前安装的对象，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2385b-130">You can use the U2 parameter to overwrite previously installed objects, as follows:</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> U2  
       ```  
  
        <span data-ttu-id="2385b-131">或多个</span><span class="sxs-lookup"><span data-stu-id="2385b-131">or</span></span>  
  
       ```  
       tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
       ```  
  
       > [!NOTE]
       >  <span data-ttu-id="2385b-132">您可以轻松地实际传输数派生 cofile 文件名称。</span><span class="sxs-lookup"><span data-stu-id="2385b-132">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="2385b-133">例如，名为 K900534 cofile。BI1 提供 BI1K900534 传输数。</span><span class="sxs-lookup"><span data-stu-id="2385b-133">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
   2.  <span data-ttu-id="2385b-134">之后`tp`命令完成，你将看到类似于以下报表：</span><span class="sxs-lookup"><span data-stu-id="2385b-134">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
       ```  
       This is tp version 320.56.66 (release 620)  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
       R3trans.exe finished (0000).  
       tp finished with return code: 0  
       ```  
  
        <span data-ttu-id="2385b-135">返回代码"0"表示操作成功。</span><span class="sxs-lookup"><span data-stu-id="2385b-135">Return code "0" means that the operation succeeded.</span></span>  
  
        <span data-ttu-id="2385b-136">返回代码为 0 或 4 是可接受的。</span><span class="sxs-lookup"><span data-stu-id="2385b-136">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="2385b-137">如果收到返回代码为 8 或更高版本，请与 Microsoft 客户服务和支持联系。</span><span class="sxs-lookup"><span data-stu-id="2385b-137">Contact Microsoft Customer Service and Support if you receive a return code of 8 or above.</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="2385b-138">传输文件的第二个集，请重复步骤 （a） 和 (b)。</span><span class="sxs-lookup"><span data-stu-id="2385b-138">Repeat steps (a) and (b) for the second set of transport files.</span></span>  
  
4. <span data-ttu-id="2385b-139">检查传输日志。</span><span class="sxs-lookup"><span data-stu-id="2385b-139">Check the transport log.</span></span>  
  
5. <span data-ttu-id="2385b-140">请查看在 SAP GUI 传输管理器中使用事务 SE09 以验证没有错误传输日志。</span><span class="sxs-lookup"><span data-stu-id="2385b-140">Check the transport log in SAP GUI Transport Organizer using transaction SE09 to verify that there are no errors.</span></span>  
  
   <span data-ttu-id="2385b-141">设置用户授权</span><span class="sxs-lookup"><span data-stu-id="2385b-141">Setting User Authorization</span></span>  
   <span data-ttu-id="2385b-142">Z_EXTRACT_DATA_OO RFC 要求使用特定的授权对象的用户 Id。</span><span class="sxs-lookup"><span data-stu-id="2385b-142">The Z_EXTRACT_DATA_OO RFC requires user IDs with specific authorization objects.</span></span> <span data-ttu-id="2385b-143">使用 SAP GUI 授权管理工具的 RFC 执行设置的最小限制：</span><span class="sxs-lookup"><span data-stu-id="2385b-143">Use the SAP GUI authorization administration tools to set the minimum restrictions on the execution of the RFC:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2385b-144">不需要设置 Z_EXECUTE_SAP_QUERY RFC 的授权。</span><span class="sxs-lookup"><span data-stu-id="2385b-144">You do not need to set the authorization for the Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
- <span data-ttu-id="2385b-145">Z_EXTRACT_DATA_OO 需要 S_TABU_DIS 和 Z_EIP_TABL。</span><span class="sxs-lookup"><span data-stu-id="2385b-145">Z_EXTRACT_DATA_OO requires both S_TABU_DIS and Z_EIP_TABL.</span></span> <span data-ttu-id="2385b-146">以下值提供 S_TABU_DIS，允许用户查看系统中的任何表的元数据的最小限制。</span><span class="sxs-lookup"><span data-stu-id="2385b-146">The following values provide the minimum restrictions for S_TABU_DIS, which allow users to view metadata for any table in the system.</span></span>  
  
  - <span data-ttu-id="2385b-147">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="2385b-147">ACTVT: 03</span></span>  
  
  - <span data-ttu-id="2385b-148">DICBERCLS: \*</span><span class="sxs-lookup"><span data-stu-id="2385b-148">DICBERCLS: \*</span></span>  
  
    <span data-ttu-id="2385b-149">DICBERCLS 可用于通过授权类来限制对表的授权。</span><span class="sxs-lookup"><span data-stu-id="2385b-149">You can use DICBERCLS to restrict authorization to tables by authorization class.</span></span>  
  
    <span data-ttu-id="2385b-150">TDDAT 表可用于查看表的授权类。</span><span class="sxs-lookup"><span data-stu-id="2385b-150">You can use the TDDAT table to view the authorization class for tables.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2385b-151">若要通过表维护事务将防止对表的更改，应仅授予在生产环境中的显示特权 (ACTVT: 03 设置允许的活动来显示)。</span><span class="sxs-lookup"><span data-stu-id="2385b-151">To prevent changes to tables by table maintenance transactions, you should only grant display privileges in a production environment (ACTVT: 03 sets the permissible activity to display).</span></span>  
  
   <span data-ttu-id="2385b-152">Z_EIP_TABL 的最小值是：</span><span class="sxs-lookup"><span data-stu-id="2385b-152">The minimum values for Z_EIP_TABL are:</span></span>  
  
  - <span data-ttu-id="2385b-153">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="2385b-153">ACTVT: 03</span></span>  
  
  - <span data-ttu-id="2385b-154">表: \*</span><span class="sxs-lookup"><span data-stu-id="2385b-154">TABLE: \*</span></span>  
  
    <span data-ttu-id="2385b-155">可以使用表来显式定义经过授权的表。</span><span class="sxs-lookup"><span data-stu-id="2385b-155">You can use TABLE to explicitly define the authorized tables.</span></span> <span data-ttu-id="2385b-156">同时请注意，S_TABU_DIS 还可在其他事务中。</span><span class="sxs-lookup"><span data-stu-id="2385b-156">Note, too, that S_TABU_DIS is also used in other transactions.</span></span>  
  
##### <a name="to-set-user-authorization"></a><span data-ttu-id="2385b-157">若要设置用户授权</span><span class="sxs-lookup"><span data-stu-id="2385b-157">To set user authorization</span></span>  
  
1.  <span data-ttu-id="2385b-158">启动将 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="2385b-158">Start the SAP GUI.</span></span> <span data-ttu-id="2385b-159">转到 T 代码，类型`pfcg`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2385b-159">Go to T-code, type `pfcg`, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="2385b-160">在中**角色**文字框中，输入你想要创建，例如，一个角色名称`ZTEST`，然后单击**角色**。</span><span class="sxs-lookup"><span data-stu-id="2385b-160">In the **Role** text box, enter a role name you want to create, for example, `ZTEST`, and then click **Role**.</span></span>  
  
3.  <span data-ttu-id="2385b-161">在中**Create Role**页上，单击**授权**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2385b-161">In the **Create Role** page, click the **Authorizations** tab.</span></span>  
  
     <span data-ttu-id="2385b-162">如果系统提示您保存角色，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="2385b-162">If prompted to save the role, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="2385b-163">在中**更改角色**页上，单击**更改授权数据**按钮。</span><span class="sxs-lookup"><span data-stu-id="2385b-163">In the **Change Roles** page, click the **Change Authorization Data** button.</span></span>  
  
5.  <span data-ttu-id="2385b-164">如果系统提示你选择从模板**选择模板**对话框中，单击**不选择模板**。</span><span class="sxs-lookup"><span data-stu-id="2385b-164">If you are prompted to select a template from the **Choose Template** dialog box, click **Do not select templates**.</span></span>  
  
6.  <span data-ttu-id="2385b-165">在中**更改角色： 授权**页上，单击**手动**按钮。</span><span class="sxs-lookup"><span data-stu-id="2385b-165">In the **Change role: Authorizations** page, click the **Manually** button.</span></span>  
  
7.  <span data-ttu-id="2385b-166">在中**手动选择的授权**框中，输入授权对象的名称`Z_EIP_TABL`然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="2385b-166">In the **Manual selection of authorizations** box, enter the name of the authorization object `Z_EIP_TABL` and press ENTER.</span></span>  
  
8.  <span data-ttu-id="2385b-167">在中**更改角色： 授权**页上，展开节点，直到您看到的文本框**活动**并**表名**。</span><span class="sxs-lookup"><span data-stu-id="2385b-167">In the **Change role: Authorizations** page, expand the nodes until you see the text boxes for **Activity** and **Table Name**.</span></span> <span data-ttu-id="2385b-168">有关**活动**文字框中，输入值`03`。</span><span class="sxs-lookup"><span data-stu-id="2385b-168">For the **Activity** text box, enter the value `03`.</span></span> <span data-ttu-id="2385b-169">有关**表名称**文字框中，输入值`*`。</span><span class="sxs-lookup"><span data-stu-id="2385b-169">For the **Table Name** text box, enter the value `*`.</span></span>  
  
9. <span data-ttu-id="2385b-170">单击**保存**按钮以生成该配置文件。</span><span class="sxs-lookup"><span data-stu-id="2385b-170">Click the **Save** button to generate the profile.</span></span>  
  
10. <span data-ttu-id="2385b-171">返回到**更改角色**页上，单击**用户**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2385b-171">Go back to the **Change Roles** page and click the **User** tab.</span></span>  
  
11. <span data-ttu-id="2385b-172">在中**用户**选项卡上，通过输入中的用户名称将分配角色的用户 ID**用户 ID**列，然后单击**用户比较**按钮。</span><span class="sxs-lookup"><span data-stu-id="2385b-172">In the **User** tab, assign a user ID for the role by entering the user name in the **User ID** column, and click the **User comparison** button.</span></span>  
  
12. <span data-ttu-id="2385b-173">在中**比较角色用户主记录**，单击**完成比较**更新主记录。</span><span class="sxs-lookup"><span data-stu-id="2385b-173">In the **Compare Role User Master Record**, click **Complete comparison** to update the master record.</span></span> <span data-ttu-id="2385b-174">当系统提示保存角色，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="2385b-174">When prompted to save the role, click **Yes**.</span></span>  
  
13. <span data-ttu-id="2385b-175">保存并退出。</span><span class="sxs-lookup"><span data-stu-id="2385b-175">Save and exit.</span></span>  
  
<span data-ttu-id="2385b-176">验证自定义 RFC 的安装</span><span class="sxs-lookup"><span data-stu-id="2385b-176">Verifying Custom RFC Installation</span></span>  
 <span data-ttu-id="2385b-177">安装自定义 Rfc 后，可以验证是否已正确安装 Rfc。</span><span class="sxs-lookup"><span data-stu-id="2385b-177">After you install the custom RFCs, you can verify whether the RFCs installed correctly.</span></span>  
  
- <span data-ttu-id="2385b-178">Z_EXECUTE_SAP_QUERY rfc，就可以做到在 SAP 系统中使用执行预定义的查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2385b-178">For Z_EXECUTE_SAP_QUERY RFC, you can do so by executing a pre-defined query in SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
- <span data-ttu-id="2385b-179">对于 Z_EXTRACT_DATA_OO RFC，可以执行，通过执行以下测试，以确认，RFC 运行，并且可随时用于在系统中。</span><span class="sxs-lookup"><span data-stu-id="2385b-179">For Z_EXTRACT_DATA_OO RFC, you can do so by performing the following tests to confirm that the RFC operates and is ready for use in your system.</span></span>  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a><span data-ttu-id="2385b-180">若要测试的 Z_EXTRACT_DATA_OO 安装</span><span class="sxs-lookup"><span data-stu-id="2385b-180">To test the installation of Z_EXTRACT_DATA_OO</span></span>  
  
1.  <span data-ttu-id="2385b-181">SAP GUI 授权管理工具中执行 SE37，函数模块 Z_EXTRACT_DATA_OO，，然后在测试模式下运行 RFC，通过按`F8`。</span><span class="sxs-lookup"><span data-stu-id="2385b-181">In the SAP GUI authorization administration tools, execute SE37, function module Z_EXTRACT_DATA_OO, and then run the RFC in test mode by pressing `F8`.</span></span> <span data-ttu-id="2385b-182">按如下所示填充参数。</span><span class="sxs-lookup"><span data-stu-id="2385b-182">Populate the parameters as follows.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="2385b-183">IN_METADATA_ONLY</span><span class="sxs-lookup"><span data-stu-id="2385b-183">IN_METADATA_ONLY</span></span>||  
    |<span data-ttu-id="2385b-184">IN_METADATA_LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="2385b-184">IN_METADATA_LANGUAGE</span></span>|<span data-ttu-id="2385b-185">EN</span><span class="sxs-lookup"><span data-stu-id="2385b-185">EN</span></span>|  
    |<span data-ttu-id="2385b-186">IN_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="2385b-186">IN_FROM_TABLE</span></span>|<span data-ttu-id="2385b-187">T000</span><span class="sxs-lookup"><span data-stu-id="2385b-187">T000</span></span>|  
    |<span data-ttu-id="2385b-188">IN_OUTPUT_MODE</span><span class="sxs-lookup"><span data-stu-id="2385b-188">IN_OUTPUT_MODE</span></span>|<span data-ttu-id="2385b-189">S</span><span class="sxs-lookup"><span data-stu-id="2385b-189">S</span></span>|  
    |<span data-ttu-id="2385b-190">IN_OUTPUT_FILENAME</span><span class="sxs-lookup"><span data-stu-id="2385b-190">IN_OUTPUT_FILENAME</span></span>||  
    |<span data-ttu-id="2385b-191">IN_USE_FIELD_EXITS</span><span class="sxs-lookup"><span data-stu-id="2385b-191">IN_USE_FIELD_EXITS</span></span>|<span data-ttu-id="2385b-192">X</span><span class="sxs-lookup"><span data-stu-id="2385b-192">X</span></span>|  
    |<span data-ttu-id="2385b-193">IN_SET_ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="2385b-193">IN_SET_ROWCOUNT</span></span>|<span data-ttu-id="2385b-194">0</span><span class="sxs-lookup"><span data-stu-id="2385b-194">0</span></span>|  
    |<span data-ttu-id="2385b-195">IN_DELIMITER</span><span class="sxs-lookup"><span data-stu-id="2385b-195">IN_DELIMITER</span></span>||  
    |<span data-ttu-id="2385b-196">IN_PACKET_SIZE</span><span class="sxs-lookup"><span data-stu-id="2385b-196">IN_PACKET_SIZE</span></span>|<span data-ttu-id="2385b-197">50,000</span><span class="sxs-lookup"><span data-stu-id="2385b-197">50,000</span></span>|  
    |<span data-ttu-id="2385b-198">IN_MAX_WRITE_ATTEMPTS</span><span class="sxs-lookup"><span data-stu-id="2385b-198">IN_MAX_WRITE_ATTEMPTS</span></span>|<span data-ttu-id="2385b-199">4</span><span class="sxs-lookup"><span data-stu-id="2385b-199">4</span></span>|  
    |<span data-ttu-id="2385b-200">IN_RETRY_DELAY</span><span class="sxs-lookup"><span data-stu-id="2385b-200">IN_RETRY_DELAY</span></span>|<span data-ttu-id="2385b-201">30</span><span class="sxs-lookup"><span data-stu-id="2385b-201">30</span></span>|  
    |<span data-ttu-id="2385b-202">IN_SQL_DATES_ON</span><span class="sxs-lookup"><span data-stu-id="2385b-202">IN_SQL_DATES_ON</span></span>||  
  
2.  <span data-ttu-id="2385b-203">单击**Execute**或按`F8`。</span><span class="sxs-lookup"><span data-stu-id="2385b-203">Click **Execute** or press `F8`.</span></span>  
  
3.  <span data-ttu-id="2385b-204">在结果窗格中，检查以下内容。</span><span class="sxs-lookup"><span data-stu-id="2385b-204">In the results pane, check the following.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="2385b-205">OUT_TABLEHEADER</span><span class="sxs-lookup"><span data-stu-id="2385b-205">OUT_TABLEHEADER</span></span>|<span data-ttu-id="2385b-206">\<T000 常规元数据\></span><span class="sxs-lookup"><span data-stu-id="2385b-206">\<T000 general metadata\></span></span>|  
    |<span data-ttu-id="2385b-207">OUT_TECHNICALSETTINGS</span><span class="sxs-lookup"><span data-stu-id="2385b-207">OUT_TECHNICALSETTINGS</span></span>|<span data-ttu-id="2385b-208">\<T000 技术的数据库级别元数据\></span><span class="sxs-lookup"><span data-stu-id="2385b-208">\<T000 technical database level metadata\></span></span>|  
    |<span data-ttu-id="2385b-209">OUT_RECORDLENGTH</span><span class="sxs-lookup"><span data-stu-id="2385b-209">OUT_RECORDLENGTH</span></span>|<span data-ttu-id="2385b-210">\<取决于 SAP 版本\></span><span class="sxs-lookup"><span data-stu-id="2385b-210">\<depends on SAP version\></span></span>|  
    |<span data-ttu-id="2385b-211">OUT_RECORDCOUNT</span><span class="sxs-lookup"><span data-stu-id="2385b-211">OUT_RECORDCOUNT</span></span>|<span data-ttu-id="2385b-212">\<确认在 T000 SE16 与系统中的客户端数\></span><span class="sxs-lookup"><span data-stu-id="2385b-212">\<confirm the number of clients in your system with SE16 on T000\></span></span>|  
    |<span data-ttu-id="2385b-213">OUT_ZDATATABLE</span><span class="sxs-lookup"><span data-stu-id="2385b-213">OUT_ZDATATABLE</span></span>|<span data-ttu-id="2385b-214">\<确认此结果与使用 SE 16 上 T000 的源数据\></span><span class="sxs-lookup"><span data-stu-id="2385b-214">\<confirm this result with the source data using SE 16 on T000\></span></span>|  
    |<span data-ttu-id="2385b-215">OUT_RETURN_TAB</span><span class="sxs-lookup"><span data-stu-id="2385b-215">OUT_RETURN_TAB</span></span>|<span data-ttu-id="2385b-216">S 001 成功</span><span class="sxs-lookup"><span data-stu-id="2385b-216">S 001 Success</span></span>|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a><span data-ttu-id="2385b-217">删除数据提供程序适用于 SAP RFC</span><span class="sxs-lookup"><span data-stu-id="2385b-217">Remove the RFC for the Data Provider for SAP</span></span>  
  
1.  <span data-ttu-id="2385b-218">在 SAP GUI 对象导航 (SE80)，查找与 ZMSBI 开发类的所有对象。</span><span class="sxs-lookup"><span data-stu-id="2385b-218">In the SAP GUI Object Navigator (SE80), find all the objects with the ZMSBI development class.</span></span>  
  
2.  <span data-ttu-id="2385b-219">在以下的字典对象文件夹中删除具有 ZMSBI 开发类的所有对象：</span><span class="sxs-lookup"><span data-stu-id="2385b-219">Delete all objects with the ZMSBI development class from the following Dictionary Objects folders:</span></span>  
  
    -   <span data-ttu-id="2385b-220">结构</span><span class="sxs-lookup"><span data-stu-id="2385b-220">Structures</span></span>  
  
    -   <span data-ttu-id="2385b-221">函数组</span><span class="sxs-lookup"><span data-stu-id="2385b-221">Function Groups</span></span>  
  
    -   <span data-ttu-id="2385b-222">已授权的对象</span><span class="sxs-lookup"><span data-stu-id="2385b-222">Authorized Object</span></span>  
  
3.  <span data-ttu-id="2385b-223">引发一个传输，并将其迁移通过 RFC （开发、 测试和生产系统，例如） 安装每个系统。</span><span class="sxs-lookup"><span data-stu-id="2385b-223">Raise a transport, and migrate it through each system where you installed an RFC (development, test, and production systems, for example).</span></span>  
  
     <span data-ttu-id="2385b-224">进一步的帮助，请联系您的 SAP 基础管理员。</span><span class="sxs-lookup"><span data-stu-id="2385b-224">For further assistance, contact your SAP Basis Administrator.</span></span>  
     
## <a name="next"></a><span data-ttu-id="2385b-225">Next</span><span class="sxs-lookup"><span data-stu-id="2385b-225">Next</span></span>
[<span data-ttu-id="2385b-226">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="2385b-226">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[<span data-ttu-id="2385b-227">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="2385b-227">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)