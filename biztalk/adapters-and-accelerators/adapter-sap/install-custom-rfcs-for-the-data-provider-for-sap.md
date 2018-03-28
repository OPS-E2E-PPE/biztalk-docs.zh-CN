---
title: 对于 SAP 数据提供程序安装自定义的 Rfc |Microsoft 文档
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aff501e5bf59d6ae22d9ad2a00e0e5ff5ad4605
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-custom-rfcs-for-the-data-provider-for-sap"></a><span data-ttu-id="31da6-102">对于 SAP 数据提供程序安装自定义的 Rfc</span><span class="sxs-lookup"><span data-stu-id="31da6-102">Install Custom RFCs for the Data Provider for SAP</span></span>
<span data-ttu-id="31da6-103">如果你想要使用用于 mySAP Business Suite.NET Framework 数据提供程序访问 SAP 系统，请安装自定义的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="31da6-103">Install the custom RFCs if you want to use the .NET Framework Data Provider for mySAP Business Suite to access the SAP system.</span></span>

<span data-ttu-id="31da6-104">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要自定义的 Rfc 执行某些 SAP 系统上的操作：</span><span class="sxs-lookup"><span data-stu-id="31da6-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires custom RFCs to perform some operations on the SAP system to:</span></span>
  
-   <span data-ttu-id="31da6-105">运行选择的操作，[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXTRACT_DATA_OO RFC。</span><span class="sxs-lookup"><span data-stu-id="31da6-105">Run the SELECT operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXTRACT_DATA_OO RFC.</span></span>  
  
-   <span data-ttu-id="31da6-106">运行 EXECQUERY 操作[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要 Z_EXECUTE_SAP_QUERY RFC。</span><span class="sxs-lookup"><span data-stu-id="31da6-106">Run the EXECQUERY operation, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
<span data-ttu-id="31da6-107">若要执行这些 SAP 系统上的操作，必须在 SAP 系统上安装这些自定义的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="31da6-107">To perform these operations on the SAP system, you must install these custom RFCs on the SAP system.</span></span> <span data-ttu-id="31da6-108">如果你选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]连同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，安装程序将复制的 RFC 传输[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]为压缩文件 (customRFC.zip) 系统上安装适配器。</span><span class="sxs-lookup"><span data-stu-id="31da6-108">If you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the Setup program copies the RFC transport for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as a compressed file (customRFC.zip) on the system where you install the adapter.</span></span> <span data-ttu-id="31da6-109">Zip 文件通常安装在*\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft.NET Framework 数据提供程序为 mySAP Business Suite*。</span><span class="sxs-lookup"><span data-stu-id="31da6-109">The zip file is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Microsoft .NET Framework Data Provider for mySAP Business Suite*.</span></span> 
  
 <span data-ttu-id="31da6-110">提取 zip 文件之后, 你将找到四个数据文件、 两个以下命名模式 K9 *。BI1 （例如，类似于 K900534。BI1)，和其他两个以下模式 R9\*。BI1 （例如，类似于 R900534。BI1)。</span><span class="sxs-lookup"><span data-stu-id="31da6-110">After extracting the zip file, you will find four data files, two following the naming pattern K9*.BI1 (for example, similar to K900534.BI1), and the other two following the pattern R9\*.BI1 (for example, similar to R900534.BI1).</span></span>  
  

  
1.  <span data-ttu-id="31da6-111">将提取的文件复制到 SAP 应用程序服务器运行适配器的计算机。</span><span class="sxs-lookup"><span data-stu-id="31da6-111">Copy the extracted files from the computer running the adapters to the SAP application server.</span></span>  
  
    1.  <span data-ttu-id="31da6-112">SAP 应用程序服务器的开发系统 SAP / 3 系统管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="31da6-112">Log in as the SAP R/3 system administrator to the SAP application server of your development system.</span></span>  
  
    2.  <span data-ttu-id="31da6-113">将具有以下命名模式： K9 \* 两个传输文件的复制。从适配器到以下目录 server 上运行的 SAP 应用程序的计算机上的安装目录的 BI1:</span><span class="sxs-lookup"><span data-stu-id="31da6-113">Copy the two transport files with the naming pattern K9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\cofiles`  
  
    3.  <span data-ttu-id="31da6-114">将具有以下命名模式： R9 \* 两个传输文件的复制。从适配器到以下目录 server 上运行的 SAP 应用程序的计算机上的安装目录的 BI1:</span><span class="sxs-lookup"><span data-stu-id="31da6-114">Copy the two transport files with the naming pattern R9\*.BI1 from the installation directory on the computer running the adapters to the following directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\data`  
  
2.  <span data-ttu-id="31da6-115">加载到 SAP 应用程序服务器上的传输缓冲区的传输。</span><span class="sxs-lookup"><span data-stu-id="31da6-115">Load the transport into the transport buffer on the SAP application server.</span></span>  
  
    1.  <span data-ttu-id="31da6-116">在命令提示符处，导航到 SAP 应用程序服务器上的传输程序目录：</span><span class="sxs-lookup"><span data-stu-id="31da6-116">At the command prompt, navigate to the transport program directory on the SAP application server:</span></span>  
  
         `<drive>:\usr\sap\trans\bin`  
  
    2.  <span data-ttu-id="31da6-117">若要载入的传输缓冲区的传输，请执行下面的命令`\usr\sap\trans\bin`目录和替换*sysid*与开发系统的系统 ID:</span><span class="sxs-lookup"><span data-stu-id="31da6-117">To load the transport into the transport buffer, execute the following command at the `\usr\sap\trans\bin` directory and replace *sysid* with the system ID of your development system:</span></span>  
  
        ```  
        tp addtobuffer <TransportNumber> <sysid> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         <span data-ttu-id="31da6-118">其中， *TransportNumber*是实际传输数 (例如 BI1K900534)。</span><span class="sxs-lookup"><span data-stu-id="31da6-118">where, *TransportNumber* is the actual transport number (for example BI1K900534).</span></span>  
  
    3.  <span data-ttu-id="31da6-119">后`tp`命令运行完以后，你将看到类似于以下报表：</span><span class="sxs-lookup"><span data-stu-id="31da6-119">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        Addtobuffer successful for TransportNumber  
        tp finished with return code: 0  
        ```  
  
         <span data-ttu-id="31da6-120">返回代码"0"意味着该操作成功。</span><span class="sxs-lookup"><span data-stu-id="31da6-120">Return code "0" means that the operation succeeded.</span></span>  
  
         <span data-ttu-id="31da6-121">返回代码为 0 或 4 是可接受的。</span><span class="sxs-lookup"><span data-stu-id="31da6-121">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="31da6-122">如果你收到返回代码的 8 或更高版本，请与 Microsoft 客户服务和支持联系。</span><span class="sxs-lookup"><span data-stu-id="31da6-122">Contact Microsoft Customer Service and Support, if you receive a return code of 8 or above.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="31da6-123">第二个系列传输文件，请重复步骤 (b) 和 (c)。</span><span class="sxs-lookup"><span data-stu-id="31da6-123">Repeat steps (b) and (c) for the second set of transport files.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="31da6-124">你可以轻松地实际传输数派生 cofile 文件名称。</span><span class="sxs-lookup"><span data-stu-id="31da6-124">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="31da6-125">例如，名为 K900534 cofile。BI1 提供传输大量 BI1K900534。</span><span class="sxs-lookup"><span data-stu-id="31da6-125">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
3.  <span data-ttu-id="31da6-126">导入 SAP 传输。</span><span class="sxs-lookup"><span data-stu-id="31da6-126">Import the transport into SAP.</span></span>  
  
    1.  <span data-ttu-id="31da6-127">执行以下命令在命令提示符：</span><span class="sxs-lookup"><span data-stu-id="31da6-127">Execute the following command at the command prompt:</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL  
        ```  
  
         <span data-ttu-id="31da6-128">替换*sysid*与开发系统的系统 ID。</span><span class="sxs-lookup"><span data-stu-id="31da6-128">Replace *sysid* with the system ID of your development system.</span></span> <span data-ttu-id="31da6-129">替换*clientnumber*具有客户端数量的开发系统。</span><span class="sxs-lookup"><span data-stu-id="31da6-129">Replace *clientnumber* with the client number of your development system.</span></span>  
  
         <span data-ttu-id="31da6-130">U2 参数可用于覆盖以前安装的对象，如下所示：</span><span class="sxs-lookup"><span data-stu-id="31da6-130">You can use the U2 parameter to overwrite previously installed objects, as follows:</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> U2  
        ```  
  
         <span data-ttu-id="31da6-131">或</span><span class="sxs-lookup"><span data-stu-id="31da6-131">or</span></span>  
  
        ```  
        tp import <TransportNumber> <sysid> client=<clientnumber> pf=TP_DOMAIN_<sysid>.PFL U2  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="31da6-132">你可以轻松地实际传输数派生 cofile 文件名称。</span><span class="sxs-lookup"><span data-stu-id="31da6-132">You can easily derive the actual transport number from the cofile file name.</span></span> <span data-ttu-id="31da6-133">例如，名为 K900534 cofile。BI1 提供传输大量 BI1K900534。</span><span class="sxs-lookup"><span data-stu-id="31da6-133">For example, a cofile named K900534.BI1 provides a transport number of BI1K900534.</span></span>  
  
    2.  <span data-ttu-id="31da6-134">后`tp`命令运行完以后，你将看到类似于以下报表：</span><span class="sxs-lookup"><span data-stu-id="31da6-134">After the `tp` command finishes, you will see a report similar to the following:</span></span>  
  
        ```  
        This is tp version 320.56.66 (release 620)  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        This is R3trans.exe version 6.08 (release 620 - 04.02.03 - 14:54:00).  
        R3trans.exe finished (0000).  
        tp finished with return code: 0  
        ```  
  
         <span data-ttu-id="31da6-135">返回代码"0"意味着该操作成功。</span><span class="sxs-lookup"><span data-stu-id="31da6-135">Return code "0" means that the operation succeeded.</span></span>  
  
         <span data-ttu-id="31da6-136">返回代码为 0 或 4 是可接受的。</span><span class="sxs-lookup"><span data-stu-id="31da6-136">A return code of 0 or 4 is acceptable.</span></span> <span data-ttu-id="31da6-137">如果你收到返回代码的 8 或更高版本，请与 Microsoft 客户服务和支持联系。</span><span class="sxs-lookup"><span data-stu-id="31da6-137">Contact Microsoft Customer Service and Support if you receive a return code of 8 or above.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="31da6-138">传输文件的第二个集，请重复步骤 （a） 和 (b)。</span><span class="sxs-lookup"><span data-stu-id="31da6-138">Repeat steps (a) and (b) for the second set of transport files.</span></span>  
  
4.  <span data-ttu-id="31da6-139">检查传输日志。</span><span class="sxs-lookup"><span data-stu-id="31da6-139">Check the transport log.</span></span>  
  
5.  <span data-ttu-id="31da6-140">检查在 SAP GUI 传输管理器中使用事务 SE09 以验证没有错误传输日志。</span><span class="sxs-lookup"><span data-stu-id="31da6-140">Check the transport log in SAP GUI Transport Organizer using transaction SE09 to verify that there are no errors.</span></span>  
  
 <span data-ttu-id="31da6-141">设置用户授权</span><span class="sxs-lookup"><span data-stu-id="31da6-141">Setting User Authorization</span></span>  
 <span data-ttu-id="31da6-142">Z_EXTRACT_DATA_OO RFC 需要具有特定的授权对象的用户 Id。</span><span class="sxs-lookup"><span data-stu-id="31da6-142">The Z_EXTRACT_DATA_OO RFC requires user IDs with specific authorization objects.</span></span> <span data-ttu-id="31da6-143">使用 SAP GUI 授权管理工具在 RFC 执行设置的最小限制：</span><span class="sxs-lookup"><span data-stu-id="31da6-143">Use the SAP GUI authorization administration tools to set the minimum restrictions on the execution of the RFC:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31da6-144">不需要设置 Z_EXECUTE_SAP_QUERY RFC 的授权。</span><span class="sxs-lookup"><span data-stu-id="31da6-144">You do not need to set the authorization for the Z_EXECUTE_SAP_QUERY RFC.</span></span>  
  
-   <span data-ttu-id="31da6-145">Z_EXTRACT_DATA_OO 需要 S_TABU_DIS 和 Z_EIP_TABL。</span><span class="sxs-lookup"><span data-stu-id="31da6-145">Z_EXTRACT_DATA_OO requires both S_TABU_DIS and Z_EIP_TABL.</span></span> <span data-ttu-id="31da6-146">以下值提供 S_TABU_DIS，允许用户在系统中查看任何表的元数据的最小限制。</span><span class="sxs-lookup"><span data-stu-id="31da6-146">The following values provide the minimum restrictions for S_TABU_DIS, which allow users to view metadata for any table in the system.</span></span>  
  
    -   <span data-ttu-id="31da6-147">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="31da6-147">ACTVT: 03</span></span>  
  
    -   <span data-ttu-id="31da6-148">DICBERCLS: \*</span><span class="sxs-lookup"><span data-stu-id="31da6-148">DICBERCLS: \*</span></span>  
  
     <span data-ttu-id="31da6-149">DICBERCLS 可用于通过授权类限制对表的授权。</span><span class="sxs-lookup"><span data-stu-id="31da6-149">You can use DICBERCLS to restrict authorization to tables by authorization class.</span></span>  
  
     <span data-ttu-id="31da6-150">TDDAT 表可用于查看表的授权类。</span><span class="sxs-lookup"><span data-stu-id="31da6-150">You can use the TDDAT table to view the authorization class for tables.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31da6-151">以防止表维护事务更改到表，你应仅授予在生产环境中的显示特权 (ACTVT: 03 设置允许的活动来显示)。</span><span class="sxs-lookup"><span data-stu-id="31da6-151">To prevent changes to tables by table maintenance transactions, you should only grant display privileges in a production environment (ACTVT: 03 sets the permissible activity to display).</span></span>  
  
     <span data-ttu-id="31da6-152">Z_EIP_TABL 的最小值是：</span><span class="sxs-lookup"><span data-stu-id="31da6-152">The minimum values for Z_EIP_TABL are:</span></span>  
  
    -   <span data-ttu-id="31da6-153">ACTVT: 03</span><span class="sxs-lookup"><span data-stu-id="31da6-153">ACTVT: 03</span></span>  
  
    -   <span data-ttu-id="31da6-154">表: \*</span><span class="sxs-lookup"><span data-stu-id="31da6-154">TABLE: \*</span></span>  
  
     <span data-ttu-id="31da6-155">可以使用表来显式定义授权的表。</span><span class="sxs-lookup"><span data-stu-id="31da6-155">You can use TABLE to explicitly define the authorized tables.</span></span> <span data-ttu-id="31da6-156">还请注意，S_TABU_DIS 还可在其他事务中。</span><span class="sxs-lookup"><span data-stu-id="31da6-156">Note, too, that S_TABU_DIS is also used in other transactions.</span></span>  
  
##### <a name="to-set-user-authorization"></a><span data-ttu-id="31da6-157">若要设置用户授权</span><span class="sxs-lookup"><span data-stu-id="31da6-157">To set user authorization</span></span>  
  
1.  <span data-ttu-id="31da6-158">启动 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="31da6-158">Start the SAP GUI.</span></span> <span data-ttu-id="31da6-159">转到 T 代码，类型`pfcg`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="31da6-159">Go to T-code, type `pfcg`, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="31da6-160">在**角色**文本框中，输入你想要创建，例如，角色名称`ZTEST`，然后单击**角色**。</span><span class="sxs-lookup"><span data-stu-id="31da6-160">In the **Role** text box, enter a role name you want to create, for example, `ZTEST`, and then click **Role**.</span></span>  
  
3.  <span data-ttu-id="31da6-161">在**创建角色**页上，单击**授权**选项卡。</span><span class="sxs-lookup"><span data-stu-id="31da6-161">In the **Create Role** page, click the **Authorizations** tab.</span></span>  
  
     <span data-ttu-id="31da6-162">如果系统提示您保存该角色，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="31da6-162">If prompted to save the role, click **Yes**.</span></span>  
  
4.  <span data-ttu-id="31da6-163">在**更改角色**页上，单击**更改授权数据**按钮。</span><span class="sxs-lookup"><span data-stu-id="31da6-163">In the **Change Roles** page, click the **Change Authorization Data** button.</span></span>  
  
5.  <span data-ttu-id="31da6-164">如果系统提示你选择的模板**选择模板**对话框中，单击**不选择模板**。</span><span class="sxs-lookup"><span data-stu-id="31da6-164">If you are prompted to select a template from the **Choose Template** dialog box, click **Do not select templates**.</span></span>  
  
6.  <span data-ttu-id="31da6-165">在**更改角色： 授权**页上，单击**手动**按钮。</span><span class="sxs-lookup"><span data-stu-id="31da6-165">In the **Change role: Authorizations** page, click the **Manually** button.</span></span>  
  
7.  <span data-ttu-id="31da6-166">在**手动选择的授权**框中，输入授权对象的名称`Z_EIP_TABL`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="31da6-166">In the **Manual selection of authorizations** box, enter the name of the authorization object `Z_EIP_TABL` and press ENTER.</span></span>  
  
8.  <span data-ttu-id="31da6-167">在**更改角色： 授权**页上，展开节点，直到你看到的文本框中**活动**和**表名**。</span><span class="sxs-lookup"><span data-stu-id="31da6-167">In the **Change role: Authorizations** page, expand the nodes until you see the text boxes for **Activity** and **Table Name**.</span></span> <span data-ttu-id="31da6-168">有关**活动**文本框中，输入值`03`。</span><span class="sxs-lookup"><span data-stu-id="31da6-168">For the **Activity** text box, enter the value `03`.</span></span> <span data-ttu-id="31da6-169">有关**表名**文本框中，输入值`*`。</span><span class="sxs-lookup"><span data-stu-id="31da6-169">For the **Table Name** text box, enter the value `*`.</span></span>  
  
9. <span data-ttu-id="31da6-170">单击**保存**按钮以生成配置文件。</span><span class="sxs-lookup"><span data-stu-id="31da6-170">Click the **Save** button to generate the profile.</span></span>  
  
10. <span data-ttu-id="31da6-171">返回到**更改角色**页上，单击**用户**选项卡。</span><span class="sxs-lookup"><span data-stu-id="31da6-171">Go back to the **Change Roles** page and click the **User** tab.</span></span>  
  
11. <span data-ttu-id="31da6-172">在**用户**选项卡上，通过输入中的用户名称将分配角色的用户 ID**用户 ID**列并单击**用户比较**按钮。</span><span class="sxs-lookup"><span data-stu-id="31da6-172">In the **User** tab, assign a user ID for the role by entering the user name in the **User ID** column, and click the **User comparison** button.</span></span>  
  
12. <span data-ttu-id="31da6-173">在**比较角色用户的主记录**，单击**完成比较**更新的主记录。</span><span class="sxs-lookup"><span data-stu-id="31da6-173">In the **Compare Role User Master Record**, click **Complete comparison** to update the master record.</span></span> <span data-ttu-id="31da6-174">当系统提示保存角色，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="31da6-174">When prompted to save the role, click **Yes**.</span></span>  
  
13. <span data-ttu-id="31da6-175">保存并退出。</span><span class="sxs-lookup"><span data-stu-id="31da6-175">Save and exit.</span></span>  
  
<span data-ttu-id="31da6-176">验证自定义的 RFC 安装</span><span class="sxs-lookup"><span data-stu-id="31da6-176">Verifying Custom RFC Installation</span></span>  
 <span data-ttu-id="31da6-177">安装自定义的 Rfc 之后，你可以验证是否正确安装了 Rfc。</span><span class="sxs-lookup"><span data-stu-id="31da6-177">After you install the custom RFCs, you can verify whether the RFCs installed correctly.</span></span>  
  
-   <span data-ttu-id="31da6-178">对于 Z_EXECUTE_SAP_QUERY RFC，您可以执行，通过执行中 SAP 系统使用的预定义的查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="31da6-178">For Z_EXECUTE_SAP_QUERY RFC, you can do so by executing a pre-defined query in SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
-   <span data-ttu-id="31da6-179">对于 Z_EXTRACT_DATA_OO RFC，您可以执行，通过执行以下测试，确认 RFC 运行，并在你的系统中可供使用。</span><span class="sxs-lookup"><span data-stu-id="31da6-179">For Z_EXTRACT_DATA_OO RFC, you can do so by performing the following tests to confirm that the RFC operates and is ready for use in your system.</span></span>  
  
##### <a name="to-test-the-installation-of-zextractdataoo"></a><span data-ttu-id="31da6-180">若要测试的 Z_EXTRACT_DATA_OO 安装</span><span class="sxs-lookup"><span data-stu-id="31da6-180">To test the installation of Z_EXTRACT_DATA_OO</span></span>  
  
1.  <span data-ttu-id="31da6-181">在 SAP GUI 授权管理工具中，执行 SE37，函数模块 Z_EXTRACT_DATA_OO，，然后在测试模式下运行 RFC，通过按`F8`。</span><span class="sxs-lookup"><span data-stu-id="31da6-181">In the SAP GUI authorization administration tools, execute SE37, function module Z_EXTRACT_DATA_OO, and then run the RFC in test mode by pressing `F8`.</span></span> <span data-ttu-id="31da6-182">如下所示填充参数。</span><span class="sxs-lookup"><span data-stu-id="31da6-182">Populate the parameters as follows.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="31da6-183">IN_METADATA_ONLY</span><span class="sxs-lookup"><span data-stu-id="31da6-183">IN_METADATA_ONLY</span></span>||  
    |<span data-ttu-id="31da6-184">IN_METADATA_LANGUAGE</span><span class="sxs-lookup"><span data-stu-id="31da6-184">IN_METADATA_LANGUAGE</span></span>|<span data-ttu-id="31da6-185">EN</span><span class="sxs-lookup"><span data-stu-id="31da6-185">EN</span></span>|  
    |<span data-ttu-id="31da6-186">IN_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="31da6-186">IN_FROM_TABLE</span></span>|<span data-ttu-id="31da6-187">T000</span><span class="sxs-lookup"><span data-stu-id="31da6-187">T000</span></span>|  
    |<span data-ttu-id="31da6-188">IN_OUTPUT_MODE</span><span class="sxs-lookup"><span data-stu-id="31da6-188">IN_OUTPUT_MODE</span></span>|<span data-ttu-id="31da6-189">S</span><span class="sxs-lookup"><span data-stu-id="31da6-189">S</span></span>|  
    |<span data-ttu-id="31da6-190">IN_OUTPUT_FILENAME</span><span class="sxs-lookup"><span data-stu-id="31da6-190">IN_OUTPUT_FILENAME</span></span>||  
    |<span data-ttu-id="31da6-191">IN_USE_FIELD_EXITS</span><span class="sxs-lookup"><span data-stu-id="31da6-191">IN_USE_FIELD_EXITS</span></span>|<span data-ttu-id="31da6-192">X</span><span class="sxs-lookup"><span data-stu-id="31da6-192">X</span></span>|  
    |<span data-ttu-id="31da6-193">IN_SET_ROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="31da6-193">IN_SET_ROWCOUNT</span></span>|<span data-ttu-id="31da6-194">0</span><span class="sxs-lookup"><span data-stu-id="31da6-194">0</span></span>|  
    |<span data-ttu-id="31da6-195">IN_DELIMITER</span><span class="sxs-lookup"><span data-stu-id="31da6-195">IN_DELIMITER</span></span>||  
    |<span data-ttu-id="31da6-196">IN_PACKET_SIZE</span><span class="sxs-lookup"><span data-stu-id="31da6-196">IN_PACKET_SIZE</span></span>|<span data-ttu-id="31da6-197">50,000</span><span class="sxs-lookup"><span data-stu-id="31da6-197">50,000</span></span>|  
    |<span data-ttu-id="31da6-198">IN_MAX_WRITE_ATTEMPTS</span><span class="sxs-lookup"><span data-stu-id="31da6-198">IN_MAX_WRITE_ATTEMPTS</span></span>|<span data-ttu-id="31da6-199">4</span><span class="sxs-lookup"><span data-stu-id="31da6-199">4</span></span>|  
    |<span data-ttu-id="31da6-200">IN_RETRY_DELAY</span><span class="sxs-lookup"><span data-stu-id="31da6-200">IN_RETRY_DELAY</span></span>|<span data-ttu-id="31da6-201">30</span><span class="sxs-lookup"><span data-stu-id="31da6-201">30</span></span>|  
    |<span data-ttu-id="31da6-202">IN_SQL_DATES_ON</span><span class="sxs-lookup"><span data-stu-id="31da6-202">IN_SQL_DATES_ON</span></span>||  
  
2.  <span data-ttu-id="31da6-203">单击**执行**或按`F8`。</span><span class="sxs-lookup"><span data-stu-id="31da6-203">Click **Execute** or press `F8`.</span></span>  
  
3.  <span data-ttu-id="31da6-204">在结果窗格中，检查以下内容。</span><span class="sxs-lookup"><span data-stu-id="31da6-204">In the results pane, check the following.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="31da6-205">OUT_TABLEHEADER</span><span class="sxs-lookup"><span data-stu-id="31da6-205">OUT_TABLEHEADER</span></span>|<span data-ttu-id="31da6-206">\<T000 常规元数据\></span><span class="sxs-lookup"><span data-stu-id="31da6-206">\<T000 general metadata\></span></span>|  
    |<span data-ttu-id="31da6-207">OUT_TECHNICALSETTINGS</span><span class="sxs-lookup"><span data-stu-id="31da6-207">OUT_TECHNICALSETTINGS</span></span>|<span data-ttu-id="31da6-208">\<T000 技术数据库级别的元数据\></span><span class="sxs-lookup"><span data-stu-id="31da6-208">\<T000 technical database level metadata\></span></span>|  
    |<span data-ttu-id="31da6-209">OUT_RECORDLENGTH</span><span class="sxs-lookup"><span data-stu-id="31da6-209">OUT_RECORDLENGTH</span></span>|<span data-ttu-id="31da6-210">\<取决于 SAP 版本\></span><span class="sxs-lookup"><span data-stu-id="31da6-210">\<depends on SAP version\></span></span>|  
    |<span data-ttu-id="31da6-211">OUT_RECORDCOUNT</span><span class="sxs-lookup"><span data-stu-id="31da6-211">OUT_RECORDCOUNT</span></span>|<span data-ttu-id="31da6-212">\<与上 T000 SE16 系统中确认客户端的数量\></span><span class="sxs-lookup"><span data-stu-id="31da6-212">\<confirm the number of clients in your system with SE16 on T000\></span></span>|  
    |<span data-ttu-id="31da6-213">OUT_ZDATATABLE</span><span class="sxs-lookup"><span data-stu-id="31da6-213">OUT_ZDATATABLE</span></span>|<span data-ttu-id="31da6-214">\<确认此结果与源数据在 T000 上使用 SE 16\></span><span class="sxs-lookup"><span data-stu-id="31da6-214">\<confirm this result with the source data using SE 16 on T000\></span></span>|  
    |<span data-ttu-id="31da6-215">OUT_RETURN_TAB</span><span class="sxs-lookup"><span data-stu-id="31da6-215">OUT_RETURN_TAB</span></span>|<span data-ttu-id="31da6-216">S 001 Success</span><span class="sxs-lookup"><span data-stu-id="31da6-216">S 001 Success</span></span>|  
  
## <a name="remove-the-rfc-for-the-data-provider-for-sap"></a><span data-ttu-id="31da6-217">对于 SAP 数据提供程序删除 RFC</span><span class="sxs-lookup"><span data-stu-id="31da6-217">Remove the RFC for the Data Provider for SAP</span></span>  
  
1.  <span data-ttu-id="31da6-218">在 SAP GUI 对象导航 (SE80)，查找与 ZMSBI 开发类的所有对象。</span><span class="sxs-lookup"><span data-stu-id="31da6-218">In the SAP GUI Object Navigator (SE80), find all the objects with the ZMSBI development class.</span></span>  
  
2.  <span data-ttu-id="31da6-219">在以下的字典对象文件夹中删除与 ZMSBI 开发类的所有对象：</span><span class="sxs-lookup"><span data-stu-id="31da6-219">Delete all objects with the ZMSBI development class from the following Dictionary Objects folders:</span></span>  
  
    -   <span data-ttu-id="31da6-220">结构</span><span class="sxs-lookup"><span data-stu-id="31da6-220">Structures</span></span>  
  
    -   <span data-ttu-id="31da6-221">函数组</span><span class="sxs-lookup"><span data-stu-id="31da6-221">Function Groups</span></span>  
  
    -   <span data-ttu-id="31da6-222">授权的对象</span><span class="sxs-lookup"><span data-stu-id="31da6-222">Authorized Object</span></span>  
  
3.  <span data-ttu-id="31da6-223">引发一个传输，并将它迁移通过 RFC （开发、 测试和生产系统，例如） 的安装位置的每个系统。</span><span class="sxs-lookup"><span data-stu-id="31da6-223">Raise a transport, and migrate it through each system where you installed an RFC (development, test, and production systems, for example).</span></span>  
  
     <span data-ttu-id="31da6-224">以获取进一步的帮助，请与您的 SAP 基础管理员联系。</span><span class="sxs-lookup"><span data-stu-id="31da6-224">For further assistance, contact your SAP Basis Administrator.</span></span>  
     
## <a name="next"></a><span data-ttu-id="31da6-225">Next</span><span class="sxs-lookup"><span data-stu-id="31da6-225">Next</span></span>
[<span data-ttu-id="31da6-226">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="31da6-226">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)  
[<span data-ttu-id="31da6-227">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="31da6-227">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)