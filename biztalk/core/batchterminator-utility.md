---
title: BatchTerminator 实用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 771241fa-7df5-4882-8430-c2f36200cc9d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 080f82993fc3c8c62b3764d496f03589bd06364e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967347"
---
# <a name="batchterminator-utility"></a><span data-ttu-id="6ce56-102">BatchTerminator 实用工具</span><span class="sxs-lookup"><span data-stu-id="6ce56-102">BatchTerminator Utility</span></span>
<span data-ttu-id="6ce56-103">使用 BatchTerminator 实用工具，您可以终止所有正在运行的用于批量处理 EDI 交换的批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="6ce56-103">The BatchTerminator utility enables you to terminate all live batching orchestrations being used to batch EDI interchanges.</span></span> <span data-ttu-id="6ce56-104">如果您正在运行大量批处理业务流程实例，并且需要终止所有这些批处理，以便对 BizTalk Server 系统执行维护，此时本实用工具将非常有用。</span><span class="sxs-lookup"><span data-stu-id="6ce56-104">This utility could prove useful if you have a large number of batching orchestration instances running, and you need to terminate all the batches in order to perform maintenance on the BizTalk server system.</span></span>  
  
 <span data-ttu-id="6ce56-105">BatchTerminator 实用工具位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6ce56-105">The BatchTerminator utility is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span> <span data-ttu-id="6ce56-106">该实用工具运行实用程序来终止批处理的业务流程实例时，将 batchterminator.log 文件中记录结果\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application 数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ce56-106">When you run the utility to terminate the batching orchestration instances, the utility will log the results in the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ce56-107">只有 32 位系统才支持 BatchTerminator 实用工具。</span><span class="sxs-lookup"><span data-stu-id="6ce56-107">The BatchTerminator utility is only supported on 32 bit systems.</span></span>  <span data-ttu-id="6ce56-108">BatchTerminator 使用 Microsoft.BizTalk.ExplorerOM 命名空间中的组件，该组件仅在从 32 位进程中使用时才受到支持。</span><span class="sxs-lookup"><span data-stu-id="6ce56-108">BatchTerminator uses components in the Microsoft.BizTalk.ExplorerOM namespace, which is only supported if used from a 32 bit process.</span></span>  
  
 <span data-ttu-id="6ce56-109">**重新启动终止的 Orchestration 实例**</span><span class="sxs-lookup"><span data-stu-id="6ce56-109">**Restarting the Terminated Orchestration Instances**</span></span>  
  
 <span data-ttu-id="6ce56-110">终止一组批处理业务流程后，可以批量重新启动这些业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="6ce56-110">After you terminate a group of batching orchestrations, you can do a bulk restart of those orchestration instances.</span></span> <span data-ttu-id="6ce56-111">您需要使用 /Activate 开关和指示被停止批处理的文件的名称和路径执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6ce56-111">You do so with the /Activate switch and the name and path of a file that indicates the batches that were stopped.</span></span> <span data-ttu-id="6ce56-112">运行本实用工具终止一组业务流程实例时，它将创建此停止批处理文件。</span><span class="sxs-lookup"><span data-stu-id="6ce56-112">When you run the utility to terminate a group of orchestration instances, the utility will create this stopped-batches file.</span></span> <span data-ttu-id="6ce56-113">停止批处理文件是 batchSettings-\<GUID\>中的.xml \<*驱动器*\>: \Documents and 设置\\<*用户名称* \>\Application 数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ce56-113">The stopped-batches file is batchSettings-\<GUID\>.xml in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span> <span data-ttu-id="6ce56-114">同时会将停止批处理文件的路径和名称保存在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="6ce56-114">The path and name of the stopped-batches file is also saved in the log file.</span></span> <span data-ttu-id="6ce56-115">使用 /activate 开关运行本实用工具时，它将根据架构对输入文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="6ce56-115">When the utility runs with the /activate switch, it validates the input file against a schema.</span></span>  
  
 <span data-ttu-id="6ce56-116">**语法**</span><span class="sxs-lookup"><span data-stu-id="6ce56-116">**Syntax**</span></span>  
  
 <span data-ttu-id="6ce56-117">使用以下语法，在命令行窗口中运行 BatchTerminator 实用工具：</span><span class="sxs-lookup"><span data-stu-id="6ce56-117">Run the BatchTerminator utility in a command-line window with the following syntax:</span></span>  
  
```  
BatchTerminator /<switch>  
```  
  
 <span data-ttu-id="6ce56-118">在运行 BatchTerminator 实用工具时，可以使用以下开关。</span><span class="sxs-lookup"><span data-stu-id="6ce56-118">You can run the BatchTerminator utility with the following switches.</span></span> <span data-ttu-id="6ce56-119">如果未提供任何开关，则使用 /terminate 选项。</span><span class="sxs-lookup"><span data-stu-id="6ce56-119">If no switch is provided, the /terminate option is used.</span></span> <span data-ttu-id="6ce56-120">如下所示，您可以输入开关的完整名称，例如 /terminate，也可以使用缩写形式，在本例中，可使用 /t。</span><span class="sxs-lookup"><span data-stu-id="6ce56-120">As indicate below, you can enter the full name of the switch, such as /terminate, or the shortened form, in this case, /t.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ce56-121">开关</span><span class="sxs-lookup"><span data-stu-id="6ce56-121">Switch</span></span>|<span data-ttu-id="6ce56-122">函数</span><span class="sxs-lookup"><span data-stu-id="6ce56-122">Function</span></span>|  
|<span data-ttu-id="6ce56-123">/?</span><span class="sxs-lookup"><span data-stu-id="6ce56-123">/?</span></span>|<span data-ttu-id="6ce56-124">显示帮助</span><span class="sxs-lookup"><span data-stu-id="6ce56-124">Displays help</span></span>|  
|<span data-ttu-id="6ce56-125">/ 终止的日志：\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="6ce56-125">/terminate -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="6ce56-126">或 /t-日志：\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="6ce56-126">or /t -log:\<*log file*\></span></span>|<span data-ttu-id="6ce56-127">向所有活动的 X12 或 EDIFACT 批处理业务流程实例发送终止控制消息。</span><span class="sxs-lookup"><span data-stu-id="6ce56-127">Sends terminate control messages to all active X12 or EDIFACT batching orchestration instances.</span></span> <span data-ttu-id="6ce56-128">该实用工具将显示操作的结果，包括它所终止的所有活动批处理业务流程实例的列表、它所找到的活动批处理业务流程数，以及它所发送的终止控制消息数。</span><span class="sxs-lookup"><span data-stu-id="6ce56-128">It displays the results of the operation, including a list of all active batch orchestration instances that it terminated, the number of active batch orchestrations that it found, and the number of terminate control messages that it sent.</span></span> <span data-ttu-id="6ce56-129">它将结果记录到文件中，batchterminator.log \<*驱动器*\>: \Documents and 设置\\<*用户名*\>\应用程序数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ce56-129">It logs the results into the batchterminator.log file in the \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder.</span></span><br /><br /> <span data-ttu-id="6ce56-130">可选的-日志： 参数使你可以指定日志文件的名称和/或你想要保存到的日志文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="6ce56-130">The optional -log: parameter enables you to specify the name of the log file and/or the path of the folder that you want the log file to be saved to.</span></span> <span data-ttu-id="6ce56-131">使用参数指定的路径和文件名称的一个示例是以下： `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`。</span><span class="sxs-lookup"><span data-stu-id="6ce56-131">An example of using the parameter to specify the path and file name is the following: `BatchTerminator.exe /terminate -log:"C:\logs\log.txt"`.</span></span> <span data-ttu-id="6ce56-132">使用参数来指定文件名称的示例只是以下： `BatchTerminator.exe /terminate -log:log.txt`。</span><span class="sxs-lookup"><span data-stu-id="6ce56-132">An example of using the parameter to specify the file name only is the following: `BatchTerminator.exe /terminate -log:log.txt`.</span></span> <span data-ttu-id="6ce56-133">如果指定的路径无效，该实用工具将使用默认路径： \<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application 数据。</span><span class="sxs-lookup"><span data-stu-id="6ce56-133">If the path specified is invalid, the utility will use the default path: \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data.</span></span> <span data-ttu-id="6ce56-134">-日志： 可以使用参数，可以使用或不 / 终止交换机。</span><span class="sxs-lookup"><span data-stu-id="6ce56-134">The -log: parameter can be used either with or without the /terminate switch.</span></span>|  
|<span data-ttu-id="6ce56-135">/print</span><span class="sxs-lookup"><span data-stu-id="6ce56-135">/print</span></span><br /><br /> <span data-ttu-id="6ce56-136">或 /p</span><span class="sxs-lookup"><span data-stu-id="6ce56-136">or /p</span></span>|<span data-ttu-id="6ce56-137">只显示当前活动批处理业务流程实例的列表，不发送终止控制消息</span><span class="sxs-lookup"><span data-stu-id="6ce56-137">Displays a listing of the current active batching orchestration instances without sending terminate control messages</span></span>|  
|<span data-ttu-id="6ce56-138">/ 激活：\<*路径*\>\\</span><span class="sxs-lookup"><span data-stu-id="6ce56-138">/activate:\<*path*\>\\</span></span><br /><span data-ttu-id="6ce56-139">batchSettings-\<*GUID*\>.xml-日志：\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="6ce56-139">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span><br /><br /> <span data-ttu-id="6ce56-140">或 /a:\<*路径*\>\\</span><span class="sxs-lookup"><span data-stu-id="6ce56-140">or /a:\<*path*\>\\</span></span><br /><span data-ttu-id="6ce56-141">batchSettings-\<*GUID*\>.xml-日志：\<*日志文件*\></span><span class="sxs-lookup"><span data-stu-id="6ce56-141">batchSettings-\<*GUID*\>.xml -log:\<*log file*\></span></span>|<span data-ttu-id="6ce56-142">重新激活以前终止的业务流程实例中的 batchSettings-列出\<GUID\>.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="6ce56-142">Reactivates the previously terminated orchestration instances that are listed in the batchSettings-\<GUID\>.xml file.</span></span> <span data-ttu-id="6ce56-143">本实用工具将根据代码中嵌入的架构对输入文件进行验证。</span><span class="sxs-lookup"><span data-stu-id="6ce56-143">The utility will validate the input file against a schema embedded in the code.</span></span> <span data-ttu-id="6ce56-144">如果输入的文件与架构不匹配，将在屏幕上显示错误消息，并退出程序。</span><span class="sxs-lookup"><span data-stu-id="6ce56-144">If the input file does not match the schema, an error message will be printed to the screen and the program will exit.</span></span><br /><br /> <span data-ttu-id="6ce56-145">如果在命令中包含 -log: 开关，则此操作会将有关重新启动操作的信息写入日志文件。</span><span class="sxs-lookup"><span data-stu-id="6ce56-145">This operation writes information about the restarting action in the log file if you include the -log: switch.</span></span>|  
  
 <span data-ttu-id="6ce56-146">**批处理激活文件的格式**</span><span class="sxs-lookup"><span data-stu-id="6ce56-146">**Format of the Batch Activation File**</span></span>  
  
 <span data-ttu-id="6ce56-147">若要重新激活以前通过使用终止 batch orchestration 实例 / 激活开关，你必须提供一个批处理激活文件 (batchSettings-\<GUID\>.xml)。</span><span class="sxs-lookup"><span data-stu-id="6ce56-147">To reactivate previously terminated batch orchestration instances by using the /activate switch, you must provide a batch activation file (batchSettings-\<GUID\>.xml).</span></span> <span data-ttu-id="6ce56-148">此文件必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="6ce56-148">This file must be in the following format:</span></span>  
  
```  
<?xml version="1.0"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" elementFormDefault="qualified" id="BatchInfo" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="BatchTerminator">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="Batch">  
          <xs:complexType>  
            <xs:attribute name="PartyName" type="xs:string" />  
            <xs:attribute name="PartyID" type="xs:int" use="required" />  
            <xs:attribute name=”BatchName” type=”xs:string” />  
            <xs:attribute name=”BatchID” type=”xs:int” use=”required” />  
            <xs:attribute name="EdiMessageType" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="prerequisites"></a><span data-ttu-id="6ce56-149">先决条件</span><span class="sxs-lookup"><span data-stu-id="6ce56-149">Prerequisites</span></span>  
 <span data-ttu-id="6ce56-150">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="6ce56-150">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="6ce56-151">必须以 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6ce56-151">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-run-the-batchterminator-utility"></a><span data-ttu-id="6ce56-152">运行 BatchTerminator 实用工具</span><span class="sxs-lookup"><span data-stu-id="6ce56-152">To run the BatchTerminator utility</span></span>  
  
1.  <span data-ttu-id="6ce56-153">在 Windows 资源管理器中，转至 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ce56-153">In Windows Explorer, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\MicrosoftEDI\BatchTerminator folder.</span></span>  
  
2.  <span data-ttu-id="6ce56-154">Enter **BatchTerminator**，包括任何所需的开关，然后单击**Enter**。</span><span class="sxs-lookup"><span data-stu-id="6ce56-154">Enter **BatchTerminator**, including any desired switches, and then click **Enter**.</span></span>  
  
3.  <span data-ttu-id="6ce56-155">在 Windows 资源管理器，移动到\<*驱动器*\>: \Documents and 设置\\<*用户名*\>\Application 数据文件夹，并打开 batchterminator.log 文件以查看结果的日志。</span><span class="sxs-lookup"><span data-stu-id="6ce56-155">In Windows Explorer, move to \<*drive*\>:\Documents and Settings\\<*user name*\>\Application Data folder, and open the batchterminator.log file to see a log of the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce56-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ce56-156">See Also</span></span>  
 [<span data-ttu-id="6ce56-157">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="6ce56-157">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)