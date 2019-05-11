---
title: 连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93e56c1f-adee-4976-bc39-bb9b8102145e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453c266739098cf6ade1f61a856d04badc330e66
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529436"
---
# <a name="connect-to-the-oracle-database-in-visual-studio-using-the-add-adapter-service-reference"></a><span data-ttu-id="19475-102">连接到 Oracle 数据库，在 Visual Studio 中使用添加适配器服务引用</span><span class="sxs-lookup"><span data-stu-id="19475-102">Connect to the Oracle Database in Visual Studio using the Add Adapter Service Reference</span></span>
<span data-ttu-id="19475-103">若要连接到 Oracle 数据库使用[!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)]在.NET 编程解决方案中，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19475-103">To connect to the Oracle database using the [!INCLUDE[adapteroracle_short_md](../../includes/adapteroracle-short-md.md)] in a .NET programming solution, you must use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="19475-104">本主题说明了如何使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19475-104">This topic provides instructions on how to use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="connect-using-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="19475-105">使用添加适配器服务引用插件进行连接</span><span class="sxs-lookup"><span data-stu-id="19475-105">Connect using the Add Adapter Service Reference Plug-in</span></span>  
<span data-ttu-id="19475-106">完成以下步骤连接到 Oracle 数据库使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="19475-106">Complete the following steps to connect to an Oracle database using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>   

  
1. <span data-ttu-id="19475-107">若要使用连接[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]编程解决方案中：</span><span class="sxs-lookup"><span data-stu-id="19475-107">To connect using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] in a programming solution:</span></span>  
  
   1.  <span data-ttu-id="19475-108">创建使用 Visual Studio 项目。</span><span class="sxs-lookup"><span data-stu-id="19475-108">Create a project using Visual Studio.</span></span>  
  
   2.  <span data-ttu-id="19475-109">右键单击解决方案资源管理器中的项目，然后单击**添加适配器服务引用**。</span><span class="sxs-lookup"><span data-stu-id="19475-109">Right-click the project in Solution Explorer, and then click **Add Adapter Service Reference**.</span></span> <span data-ttu-id="19475-110">此时将打开添加适配器服务引用插件。</span><span class="sxs-lookup"><span data-stu-id="19475-110">The Add Adapter Service Reference Plug-in opens.</span></span>  
  
2. <span data-ttu-id="19475-111">从**选择绑定**下拉列表中，选择**oracleDBBinding**然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="19475-111">From the **Select a binding** drop-down list, select **oracleDBBinding** and click **Configure**.</span></span>  
  
3. <span data-ttu-id="19475-112">在中**配置适配器**对话框中，单击**安全**选项卡上，并从**客户端凭据类型**下拉列表框中，选择**用户名**并指定用户名和密码以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="19475-112">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database.</span></span>  
  
   1. <span data-ttu-id="19475-113">若要使用 Oracle 数据库凭据进行连接，请键入中的数据库凭据**用户名**并**密码**文本框。</span><span class="sxs-lookup"><span data-stu-id="19475-113">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span> <span data-ttu-id="19475-114">请确保指定的用户名和密码以连接到 Oracle 数据库时遵循以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="19475-114">Make sure you adhere to the following considerations when specifying the user name and password to connect to an Oracle database:</span></span>  
  
      - <span data-ttu-id="19475-115">**用户名称**。</span><span class="sxs-lookup"><span data-stu-id="19475-115">**User name**.</span></span> <span data-ttu-id="19475-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的用户名的值的大小写。</span><span class="sxs-lookup"><span data-stu-id="19475-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the user name when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="19475-117">对 Oracle 数据库用户名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="19475-117">User names on the Oracle database are case-sensitive.</span></span> <span data-ttu-id="19475-118">应确保提供 Oracle 用户名称[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在所需的 Oracle 数据库的情况下。</span><span class="sxs-lookup"><span data-stu-id="19475-118">You should ensure that you provide Oracle user names to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in the case expected by your Oracle database.</span></span> <span data-ttu-id="19475-119">通常情况下，这意味着在 SCOTT/TIGER 凭据的用户名称应为大写："SCOTT"。</span><span class="sxs-lookup"><span data-stu-id="19475-119">Typically, this means that the user name in the SCOTT/TIGER credential should be upper case: "SCOTT".</span></span>  
  
      - <span data-ttu-id="19475-120">**密码**。</span><span class="sxs-lookup"><span data-stu-id="19475-120">**Password**.</span></span> <span data-ttu-id="19475-121">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将保留在打开对 Oracle 数据库的连接时输入的密码值的大小写。</span><span class="sxs-lookup"><span data-stu-id="19475-121">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] preserves the case of the value that you enter for the password when it opens a connection on the Oracle database.</span></span> <span data-ttu-id="19475-122">对于发行版 10g 和更早版本，不区分大小写上 Oracle 系统的密码。</span><span class="sxs-lookup"><span data-stu-id="19475-122">For release 10g and earlier, passwords on the Oracle system are not case-sensitive.</span></span>  
  
   2. <span data-ttu-id="19475-123">若要使用 Windows 身份验证进行连接，请键入**/** 中**用户名**文本框中，保留**密码**文本框保留为空。</span><span class="sxs-lookup"><span data-stu-id="19475-123">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
4. <span data-ttu-id="19475-124">单击**URI 属性**选项卡，并指定连接参数的值。</span><span class="sxs-lookup"><span data-stu-id="19475-124">Click the **URI Properties** tab, and specify values for the connection parameters.</span></span> <span data-ttu-id="19475-125">有关详细信息的连接 URI 对于[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[创建的 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="19475-125">For more information about the connection URI for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
5. <span data-ttu-id="19475-126">单击**绑定属性**选项卡，然后指定绑定属性的值，如果你想要针对的操作，任何需要。</span><span class="sxs-lookup"><span data-stu-id="19475-126">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="19475-127">例如，如果你想要面向 POLLINGSTMT 操作，则必须设置**PollingStatement**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="19475-127">For example, if you want to target the POLLINGSTMT operation, you must set the **PollingStatement** binding property.</span></span> <span data-ttu-id="19475-128">有关绑定属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="19475-128">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>
  
6. <span data-ttu-id="19475-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="19475-129">Click **OK**.</span></span>  
  
7. <span data-ttu-id="19475-130">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="19475-130">Click **Connect**.</span></span> <span data-ttu-id="19475-131">建立连接后，连接状态显示为**已连接**。</span><span class="sxs-lookup"><span data-stu-id="19475-131">After the connection is established, the connection status is shown as **Connected**.</span></span>  
  
    <span data-ttu-id="19475-132">下图显示[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]立即建立连接后。</span><span class="sxs-lookup"><span data-stu-id="19475-132">The following figure shows the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] immediately after the connection is established.</span></span>  
  
    <span data-ttu-id="19475-133">![使用适配器服务连接对话框](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span><span class="sxs-lookup"><span data-stu-id="19475-133">![Consume Adapter Service dialog box connected](../../adapters-and-accelerators/adapter-oracle-database/media/b5bdb08c-4326-408b-8c2a-aedae64925c8.gif "b5bdb08c-4326-408b-8c2a-aedae64925c8")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19475-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="19475-134">See Also</span></span>  
 <span data-ttu-id="19475-135">[连接到 Visual Studio 中的 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="19475-135">[Connect to Oracle Database in Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio.md) </span></span>  
 [<span data-ttu-id="19475-136">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="19475-136">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)