---
title: "连接到 Oracle 数据库在 Visual Studio 中使用添加适配器服务引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93e56c1f-adee-4976-bc39-bb9b8102145e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12c815fbfe2b723a0dd4e4646fd7b69a7e30b01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-oracle-database-in-visual-studio-using-the-add-adapter-service-reference"></a><span data-ttu-id="fc6d5-102">连接到 Oracle 数据库在 Visual Studio 中使用添加适配器服务引用</span><span class="sxs-lookup"><span data-stu-id="fc6d5-102">Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference</span></span>
<span data-ttu-id="fc6d5-103">若要连接到 Oracle 数据库使用[!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)]在.NET 编程解决方案中，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-103">To connect to the Oracle database using the [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="fc6d5-104">本主题将说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connect-using-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="fc6d5-105">使用添加适配器服务引用插件进行连接</span><span class="sxs-lookup"><span data-stu-id="fc6d5-105">Connect using the Add Adapter Service Reference Plug-in</span></span>  
<span data-ttu-id="fc6d5-106">完成以下步骤以连接到 Oracle 数据库使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-106">Complete the following steps to connect to an Oracle database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>   

  
1.  <span data-ttu-id="fc6d5-107">若要使用连接[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]编程解决方案中：</span><span class="sxs-lookup"><span data-stu-id="fc6d5-107">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a programming solution:</span></span>  
  
    1.  <span data-ttu-id="fc6d5-108">创建使用 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-108">Create a project using Visual Studio.</span></span>  
  
    2.  <span data-ttu-id="fc6d5-109">右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-109">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="fc6d5-110">添加适配器服务引用插件将打开。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-110">The Add Adapter Service Reference Plug-in opens.</span></span>  
  
2.  <span data-ttu-id="fc6d5-111">从**选择的绑定**下拉列表中，选择**oracleDBBinding**单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-111">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="fc6d5-112">在**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**和指定的用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-112">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
    1.  <span data-ttu-id="fc6d5-113">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**和**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-113">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="fc6d5-114">请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="fc6d5-114">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
        -   <span data-ttu-id="fc6d5-115">**用户名称**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-115">**User name**.</span></span> <span data-ttu-id="fc6d5-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="fc6d5-117">对 Oracle 数据库的用户名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-117">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="fc6d5-118">您应该确保你提供到的 Oracle 用户名[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在 Oracle 数据库所需的情况下。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-118">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="fc6d5-119">通常，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写形式:"SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-119">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
        -   <span data-ttu-id="fc6d5-120">**密码**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-120">**Password**.</span></span> <span data-ttu-id="fc6d5-121">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]保留在打开对 Oracle 数据库的连接时输入的密码的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-121">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="fc6d5-122">对于发行版 10g 和更早版本，Oracle 系统上的密码是不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-122">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
    2.  <span data-ttu-id="fc6d5-123">若要使用 Windows 身份验证进行连接，请键入 **/** 中**用户名**文本框和离开**密码**文本框保留为空白。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-123">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4.  <span data-ttu-id="fc6d5-124">单击**URI 属性**选项卡，然后指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="fc6d5-125">有关连接 URI 的详细信息为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-125">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5.  <span data-ttu-id="fc6d5-126">单击**绑定属性**选项卡上，然后指定绑定属性的值，如果任何，所需的要设定为目标的操作。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-126">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="fc6d5-127">例如，如果你想要针对 POLLINGSTMT 操作，则必须设置**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-127">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="fc6d5-128">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-128">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
6.  <span data-ttu-id="fc6d5-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-129">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="fc6d5-130">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-130">Click **Connect**.</span></span> <span data-ttu-id="fc6d5-131">建立连接后，连接状态将显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-131">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
     <span data-ttu-id="fc6d5-132">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="fc6d5-132">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
     <span data-ttu-id="fc6d5-133">![使用适配器服务连接的对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="fc6d5-133">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6d5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc6d5-134">See Also</span></span>  
 <span data-ttu-id="fc6d5-135">[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="fc6d5-135">[Connect to Oracle Database in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span></span>  
 [<span data-ttu-id="fc6d5-136">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="fc6d5-136">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)