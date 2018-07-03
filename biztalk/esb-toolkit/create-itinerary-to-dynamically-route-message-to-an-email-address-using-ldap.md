---
title: 如何： 创建路线以便动态地将消息路由到电子邮件地址使用的 LDAP 查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a2237b76524488d7a3903468ebb321d19ae623
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987598"
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a><span data-ttu-id="aec80-102">如何： 创建路线以便动态地将消息路由到电子邮件地址使用的 LDAP 查询</span><span class="sxs-lookup"><span data-stu-id="aec80-102">How to: Create an Itinerary to Dynamically Route a Message to an Email Address Using an LDAP Query</span></span>
## <a name="goal"></a><span data-ttu-id="aec80-103">目的</span><span class="sxs-lookup"><span data-stu-id="aec80-103">Goal</span></span>  
 <span data-ttu-id="aec80-104">本部分演示如何创建路线的查询通过 LDAP （轻型目录访问协议） 的电子邮件地址，然后将电子邮件发送到使用 BizTalk Server SMTP 适配器的解析终结点。</span><span class="sxs-lookup"><span data-stu-id="aec80-104">This section demonstrates how to create an itinerary that queries an e-mail address through LDAP (Lightweight Directory Access Protocol) and then sends an e-mail message to the resolved endpoint using the BizTalk Server SMTP adapter.</span></span>  
  
 <span data-ttu-id="aec80-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="aec80-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="aec80-106">创建路线传送名单以动态方式路由消息使用的 LDAP 查询。</span><span class="sxs-lookup"><span data-stu-id="aec80-106">Create an itinerary routing slip to dynamically route a message using an LDAP query.</span></span>  
  
-   <span data-ttu-id="aec80-107">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="aec80-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aec80-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="aec80-108">Prerequisites</span></span>  
 <span data-ttu-id="aec80-109">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="aec80-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
 <span data-ttu-id="aec80-110">将在其完成本部分中的计算机必须具备 Microsoft Active Directory 目录服务配置并且正在运行 (它不是所需的计算机是域控制器，但必须连接到域)。</span><span class="sxs-lookup"><span data-stu-id="aec80-110">The computer on which you will complete this section must have Microsoft Active Directory directory service configured and running (it is not required that the computer is the domain controller, but it must be connected to the domain).</span></span> <span data-ttu-id="aec80-111">此外，SMTP 服务器必须配置并可运行;若要测试本操作指南主题的结果，您必须具有要检查电子邮件发送的 ESB 的客户端。</span><span class="sxs-lookup"><span data-stu-id="aec80-111">Also, an SMTP server must be configured and running; in order to test the outcome of this How-to topic, you must have a client with which to check the e-mail sent by the ESB.</span></span>  
  
 <span data-ttu-id="aec80-112">在本部分中的说明假定组织名 Global Bank 具有 globalbank.com，域为与 Active Directory 组织单位名为 Employees 的包含的用户 John Evans 具有有效的电子邮件地址在其配置文件 （例如johne@globalbank.com).</span><span class="sxs-lookup"><span data-stu-id="aec80-112">The instructions in this section assume an organization named Global Bank, with a domain of globalbank.com, with an Active Directory Organizational Unit named Employees that contains a user named John Evans with a valid e-mail address in his profile (such as johne@globalbank.com).</span></span> <span data-ttu-id="aec80-113">不需要复制这些环境因素;但是，为了重新创建此环境中的实现，请考虑这些因素，请根据需要替换项。</span><span class="sxs-lookup"><span data-stu-id="aec80-113">It is not necessary to replicate these environmental factors; however, for purposes of recreating this implementation in your environment, please account for these factors and make substitutions as necessary.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="aec80-114">步骤</span><span class="sxs-lookup"><span data-stu-id="aec80-114">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a><span data-ttu-id="aec80-115">若要创建的 ESB 路线域特定语言 (DSL) 模型</span><span class="sxs-lookup"><span data-stu-id="aec80-115">To create an ESB itinerary domain-specific language (DSL) model</span></span>  
  
1.  <span data-ttu-id="aec80-116">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="aec80-116">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="aec80-117">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="aec80-117">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="aec80-118">在中**添加新项**对话框中，键入**LdapResolution**中**名称**框，并单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="aec80-118">In the **Add New Item** dialog box, type **LdapResolution** in the **Name** box, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="aec80-119">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="aec80-119">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="aec80-120">在 Visual Studio 中，单击的设计图面**LdapResolution.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="aec80-120">In Visual Studio, click the design surface of **LdapResolution.itinerary**.</span></span> <span data-ttu-id="aec80-121">在中**LdapResolution**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-121">In the **LdapResolution** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aec80-122">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="aec80-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="aec80-123">下**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="aec80-123">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="aec80-124">在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\LdapResolution**中**文件名**框，并单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="aec80-124">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\LdapResolution** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="aec80-125">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="aec80-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="aec80-126">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="aec80-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="aec80-127">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="aec80-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="aec80-128">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="aec80-128">To define the structure of the itinerary</span></span>  
  
1. <span data-ttu-id="aec80-129">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="aec80-130">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="aec80-131">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="aec80-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
   2.  <span data-ttu-id="aec80-132">在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
   3.  <span data-ttu-id="aec80-133">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="aec80-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
   4.  <span data-ttu-id="aec80-134">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="aec80-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2. <span data-ttu-id="aec80-135">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="aec80-136">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="aec80-137">单击**名称**属性，并键入**RouteMessageEmail**。</span><span class="sxs-lookup"><span data-stu-id="aec80-137">Click the **Name** property, and then type **RouteMessageEmail**.</span></span>  
  
   2.  <span data-ttu-id="aec80-138">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="aec80-139">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="aec80-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="aec80-140">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
   3.  <span data-ttu-id="aec80-141">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="aec80-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
   4.  <span data-ttu-id="aec80-142">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="aec80-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3. <span data-ttu-id="aec80-143">右键单击**冲突解决程序**系列**RouteMessageEmail**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="aec80-143">Right-click the **Resolver** collection of the **RouteMessageEmail** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="aec80-144">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="aec80-145">单击**名称**属性，并键入**LdapResolver**。</span><span class="sxs-lookup"><span data-stu-id="aec80-145">Click the **Name** property, and then type **LdapResolver**.</span></span>  
  
   2.  <span data-ttu-id="aec80-146">在中**解析程序实现**下拉列表中，单击**LDAP 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="aec80-146">In the **Resolver Implementation** drop-down list, click **LDAP Resolver Extension**.</span></span>  
  
   3.  <span data-ttu-id="aec80-147">在中**传输名称**下拉列表中，单击**SMTP**。</span><span class="sxs-lookup"><span data-stu-id="aec80-147">In the **Transport Name** drop-down list, click **SMTP**.</span></span>  
  
   4.  <span data-ttu-id="aec80-148">单击**传输位置**属性，并键入 **{邮件}**</span><span class="sxs-lookup"><span data-stu-id="aec80-148">Click the **Transport Location** property, and then type **{mail}**</span></span>  
  
   5.  <span data-ttu-id="aec80-149">单击**SearchRoot**属性，并键入**ou = Employees，dc = globalbank，dc = com**</span><span class="sxs-lookup"><span data-stu-id="aec80-149">Click the **SearchRoot** property, and then type **ou=Employees,dc=globalbank,dc=com**</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="aec80-150">如果你未在"先决条件"部分中设置你的环境根据规范，替换上述属性中的值与适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="aec80-150">If you have not set up your environment according to the specifications in the "Prerequisites" section, replace the values in the preceding property with ones that are appropriate for your environment.</span></span>  
  
   6.  <span data-ttu-id="aec80-151">单击**筛选器**属性，然后将值更改为 **(&(objectClass=User) (&#124;(givenName = john)))**</span><span class="sxs-lookup"><span data-stu-id="aec80-151">Click the **Filter** property, and then change the value to **(&(objectClass=User)(&#124;(givenName=john)))**</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="aec80-152">键入前面的值来替换现有文本。</span><span class="sxs-lookup"><span data-stu-id="aec80-152">Type the preceding value to replace the existing text.</span></span>  
  
   7.  <span data-ttu-id="aec80-153">在中**ThrowErrorIfNotFound**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="aec80-153">In the **ThrowErrorIfNotFound** drop-down list, click **True**.</span></span>  
  
4. <span data-ttu-id="aec80-154">在属性窗口中，单击**终结点配置**属性，然后单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="aec80-154">In the Properties window, click the **Endpoint Configuration** property, and then click the ellipsis button (...).</span></span>  
  
   1. <span data-ttu-id="aec80-155">在中**终结点配置**对话框中，单击**EmailBodyText**属性，并键入**顺序已准备好处理**。</span><span class="sxs-lookup"><span data-stu-id="aec80-155">In the **Endpoint Configuration** dialog box, click the **EmailBodyText** property, and then type **Order is ready to be processed**.</span></span>  
  
   2. <span data-ttu-id="aec80-156">单击**从**属性，并键入<strong>orders@globalbank.com</strong>。</span><span class="sxs-lookup"><span data-stu-id="aec80-156">Click the **From** property, and then type <strong>orders@globalbank.com</strong>.</span></span>  
  
   3. <span data-ttu-id="aec80-157">单击**MessagePartsAttachment**属性，并键入**2**。</span><span class="sxs-lookup"><span data-stu-id="aec80-157">Click the **MessagePartsAttachment** property, and then type **2**.</span></span>  
  
   4. <span data-ttu-id="aec80-158">单击**使用者**属性，并键入**顺序 {givenName}**。</span><span class="sxs-lookup"><span data-stu-id="aec80-158">Click the **Subject** property, and then type **Order for {givenName}**.</span></span>  
  
   5. <span data-ttu-id="aec80-159">配置**SMTPAuthentication、 SMTPHost、 用户名、** 并**密码**对于本地环境中使用的连接信息的属性。</span><span class="sxs-lookup"><span data-stu-id="aec80-159">Configure the **SMTPAuthentication, SMTPHost, UserName,** and **Password** properties using the connection information for your local environment.</span></span>  
  
   6. <span data-ttu-id="aec80-160">单击**确定**以关闭**终结点配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="aec80-160">Click **OK** to close the **Endpoint Configuration** dialog box.</span></span>  
  
5. <span data-ttu-id="aec80-161">右键单击**LdapResolver**冲突解决程序，并单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="aec80-161">Right-click the **LdapResolver** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
6. <span data-ttu-id="aec80-162">在输出窗口中，验证是否已解析中的主题**终结点配置**值是**使 John**，然后验证已解析**传输位置**是电子邮件地址与在 Active Directory 中的用户的帐户相关联 (例如， johne@globalbank.com)。</span><span class="sxs-lookup"><span data-stu-id="aec80-162">In the Output window, verify the subject in the resolved **Endpoint Configuration** value is **Order for John**, and then verify that the resolved **Transport Location** is the e-mail address associated with the user's account in Active Directory (for example, johne@globalbank.com).</span></span>  
  
7. <span data-ttu-id="aec80-163">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-163">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aec80-164">将从连接**ReceiveNAOrder**到模型元素**RouteMessageEmail**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-164">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessageEmail** model element.</span></span>  
  
8. <span data-ttu-id="aec80-165">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteMessageEmail**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-165">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteMessageEmail** model element.</span></span> <span data-ttu-id="aec80-166">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-166">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
   1.  <span data-ttu-id="aec80-167">单击**名称**属性，并键入**EmailNAOrderDoc**。</span><span class="sxs-lookup"><span data-stu-id="aec80-167">Click the **Name** property, and then type **EmailNAOrderDoc**.</span></span>  
  
   2.  <span data-ttu-id="aec80-168">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-168">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
   3.  <span data-ttu-id="aec80-169">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="aec80-169">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
   4.  <span data-ttu-id="aec80-170">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="aec80-170">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
9. <span data-ttu-id="aec80-171">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteMessageEmail**模型元素和**EmailNAOrderDoc**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-171">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteMessageEmail** model element and the **EmailNAOrderDoc** model element.</span></span> <span data-ttu-id="aec80-172">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="aec80-172">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="aec80-173">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="aec80-173">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="aec80-174">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-174">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="aec80-175">在中**关闭负载增加**下拉列表中，展开**EmailNAOrderDoc**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="aec80-175">In the **Off-Ramp** drop-down list, expand **EmailNAOrderDoc**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="aec80-176">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-176">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aec80-177">将从连接**RouteMessageEmail**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-177">Drag a connection from the **RouteMessageEmail** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="aec80-178">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="aec80-178">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="aec80-179">将从连接**SendPortFilter**到模型元素**EmailNAOrderDoc**模型元素。</span><span class="sxs-lookup"><span data-stu-id="aec80-179">Drag a connection from the **SendPortFilter** model element to the **EmailNAOrderDoc** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="aec80-180">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="aec80-180">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="aec80-181">在 Visual Studio 中，右键单击设计图面的**LdapResolution**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="aec80-181">In Visual Studio, right-click the design surface of the **LdapResolution** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aec80-182">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="aec80-182">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="aec80-183">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="aec80-183">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="aec80-184">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (LdapResolution.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="aec80-184">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (LdapResolution.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="aec80-185">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="aec80-185">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="aec80-186">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="aec80-186">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="aec80-187">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="aec80-187">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="aec80-188">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="aec80-188">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="aec80-189">选择**LdapResolution.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="aec80-189">Select **LdapResolution.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="aec80-190">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="aec80-190">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="aec80-191">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="aec80-191">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="aec80-192">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="aec80-192">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="aec80-193">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="aec80-193">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="aec80-194">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="aec80-194">Click the **Submit Request** button.</span></span> <span data-ttu-id="aec80-195">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="aec80-195">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="aec80-196">打开 Microsoft Outlook Express （或所选的邮件客户端），并验证消息传递到 John Evans 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aec80-196">Open Microsoft Outlook Express (or the mail client of your choice) and verify delivery of the message to the e-mail of John Evans.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="aec80-197">其他资源</span><span class="sxs-lookup"><span data-stu-id="aec80-197">Additional Resources</span></span>  
 <span data-ttu-id="aec80-198">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="aec80-198">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="aec80-199">开发活动</span><span class="sxs-lookup"><span data-stu-id="aec80-199">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="aec80-200">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="aec80-200">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)