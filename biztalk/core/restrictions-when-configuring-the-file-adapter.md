---
title: 配置文件适配器时的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], restrictions
- File adapters, restrictions
ms.assetid: 8d8137a7-5b16-4ae3-a0a7-6d114324bdf3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c866dc6bfed3e378105b7055b312a832598c22d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399098"
---
# <a name="restrictions-when-configuring-the-file-adapter"></a><span data-ttu-id="903fc-102">配置文件适配器时的限制</span><span class="sxs-lookup"><span data-stu-id="903fc-102">Restrictions when configuring the File adapter</span></span>
<span data-ttu-id="903fc-103">限制和规则时使用文件适配器。</span><span class="sxs-lookup"><span data-stu-id="903fc-103">Restrictions and rules when using the file adapter.</span></span>

## <a name="file-mask-and-file-name-gotchas"></a><span data-ttu-id="903fc-104">文件掩码和文件名称陷阱</span><span class="sxs-lookup"><span data-stu-id="903fc-104">File mask and file name gotchas</span></span>

<span data-ttu-id="903fc-105">文件掩码是文件的一个字符串，指定文件接收处理程序将从接收位置提取的类型。</span><span class="sxs-lookup"><span data-stu-id="903fc-105">The file mask is a string that specifies the type of file that the File receive handler will pick up from the receive location.</span></span> <span data-ttu-id="903fc-106">文件名称是文件的一个字符串，指定文件发送处理程序将在其中写入消息的名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-106">The file name is a string that specifies the name of the file where the File send handler will write the message.</span></span>  
  
 <span data-ttu-id="903fc-107">以下限制适用于文件的名称和文件掩码属性：</span><span class="sxs-lookup"><span data-stu-id="903fc-107">The following restrictions apply to the file name and file mask properties:</span></span>  
  
- <span data-ttu-id="903fc-108">接收位置或发送端口可以每个指定只有一个文件掩码或文件名。</span><span class="sxs-lookup"><span data-stu-id="903fc-108">Only one file mask or file name can be specified per receive location or send port.</span></span>  
  
- <span data-ttu-id="903fc-109">不允许的完整路径或文件掩码或文件名以及路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="903fc-109">The full path or part of the path along with the file mask or file name is not allowed.</span></span> <span data-ttu-id="903fc-110">文件掩码和文件名始终表示不带路径的名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-110">The file mask and file name always represent a name without the path.</span></span>  
  
- <span data-ttu-id="903fc-111">文件掩码和文件名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="903fc-111">The file mask and file name are not case-sensitive.</span></span>  
  
- <span data-ttu-id="903fc-112">文件名称不能包含任何以下字符： \< \> : / &#124; "？</span><span class="sxs-lookup"><span data-stu-id="903fc-112">The file name cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="903fc-113">\* ;</span><span class="sxs-lookup"><span data-stu-id="903fc-113">\* ;</span></span>  
  
- <span data-ttu-id="903fc-114">文件掩码不能包含任何以下字符： \< \> : / &#124; ";</span><span class="sxs-lookup"><span data-stu-id="903fc-114">The file mask cannot contain any of the following characters: \< \> : / &#124; " ;</span></span> 
  
- <span data-ttu-id="903fc-115">以下保留的设备名称不能用作文件的名称：CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。</span><span class="sxs-lookup"><span data-stu-id="903fc-115">The following reserved device names cannot be used as the name of a file: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span> <span data-ttu-id="903fc-116">此外，不允许的那些扩展的任何组合。</span><span class="sxs-lookup"><span data-stu-id="903fc-116">In addition, any combinations of these with extensions are not allowed.</span></span>  
  
- <span data-ttu-id="903fc-117">Windows 磁盘卷使用 8.3 （8.3 文件名） 默认情况下使用短期和长期的文件的名称命名约定。</span><span class="sxs-lookup"><span data-stu-id="903fc-117">Windows disk volumes use the 8.3 (8dot3) naming convention by default, which uses short and long file names.</span></span> <span data-ttu-id="903fc-118">非系统磁盘卷禁用 8.3 文件名的命名约定，并因此仅使用长文件名。</span><span class="sxs-lookup"><span data-stu-id="903fc-118">Non-system disk volumes disable the 8dot3 naming convention, and therefore only use long file names.</span></span> 

  <span data-ttu-id="903fc-119">启用 8dot3 后，文件和其文件扩展名地转换为短名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-119">When 8dot3 is enabled, files and their file extensions get converted to a short name.</span></span> <span data-ttu-id="903fc-120">例如，`testabcdefgh.docx`将转换为`testab~1.doc`。</span><span class="sxs-lookup"><span data-stu-id="903fc-120">For example, `testabcdefgh.docx` gets converted to `testab~1.doc`.</span></span> <span data-ttu-id="903fc-121">请注意，缩短文件名，并且从缩短的文件扩展名`.docx`到`doc`。</span><span class="sxs-lookup"><span data-stu-id="903fc-121">Notice that file name is shortened, and the file extension is shortened from `.docx` to `doc`.</span></span>

  <span data-ttu-id="903fc-122">此行为会影响文件适配器接收文件的方式。</span><span class="sxs-lookup"><span data-stu-id="903fc-122">This behavior impacts how the File adapter receives file.</span></span> <span data-ttu-id="903fc-123">如果文件掩码设置为`*.xml`，然后文件匹配两者`*.xml`和`*.xmln`提取扩展。</span><span class="sxs-lookup"><span data-stu-id="903fc-123">If a file mask is set to `*.xml`, then files matching both `*.xml` and `*.xmln` extensions are picked up.</span></span> 

  <span data-ttu-id="903fc-124">若要查看是否对磁盘上启用 8dot3 命名约定，打开命令提示符下，作为管理员，并键入`fsutil 8dot3name query c:`，或`fsutil 8dot3name query d:`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="903fc-124">To see if the 8dot3 naming convention is enabled on your disks, open a command prompt as Administrator, and type `fsutil 8dot3name query c:`, or `fsutil 8dot3name query d:`, and so on.</span></span> <span data-ttu-id="903fc-125">示例输出如以下所示：</span><span class="sxs-lookup"><span data-stu-id="903fc-125">Sample output looks like the following:</span></span>

  ```
  C:\WINDOWS\system32>fsutil 8dot3name query c:
  The volume state is: 0 (8dot3 name creation is enabled).
  The registry state is: 2 (Per volume setting - the default).
    
  Based on the above two settings, 8dot3 name creation is enabled on c:
  ```
    
  <span data-ttu-id="903fc-126">文件适配器将使用[FindFirstFile 函数](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="903fc-126">The File adapter uses the [FindFirstFile function](https://msdn.microsoft.com/library/windows/desktop/aa364418(v=vs.85).aspx).</span></span> <span data-ttu-id="903fc-127">此函数包含具有短期和长期的文件名的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="903fc-127">This function includes search results that have the short and long file names.</span></span> <span data-ttu-id="903fc-128">若要查看文件夹中的短期和长期文件名称，打开命令提示符处，转到您的文件夹，然后键入`dir /x`。</span><span class="sxs-lookup"><span data-stu-id="903fc-128">To see the short and long file names in a folder, open a command prompt, go to your folder, and type `dir /x`.</span></span> <span data-ttu-id="903fc-129">在命令提示符中，您可以键入`dir c:\foldername /x`。</span><span class="sxs-lookup"><span data-stu-id="903fc-129">In a command prompt, you can also type `dir c:\foldername /x`.</span></span>
    
  <span data-ttu-id="903fc-130">如果您更改的卷上的 8dot3name 设置，新的文件使用新的设置。</span><span class="sxs-lookup"><span data-stu-id="903fc-130">If you change the 8dot3name setting on a volume, then new files use the new setting.</span></span> <span data-ttu-id="903fc-131">任何现有文件将其名称，直至它们也会移动。</span><span class="sxs-lookup"><span data-stu-id="903fc-131">Any existing files keep their names until they are moved.</span></span> 
    
  <span data-ttu-id="903fc-132">若要仅选取你预期的文件，并在更高版本的加载过程中获得更佳性能 （更少的开销），则它可能是最佳配置文件适配器以使用卷在禁用 8dot3name。</span><span class="sxs-lookup"><span data-stu-id="903fc-132">To only pick up your intended files, and to get better performance (less overhead) during higher load, then it may be best to configure the File adapter to use a volume where 8dot3name is disabled.</span></span> 
  
- <span data-ttu-id="903fc-133">文件路径、 文件掩码和文件名 （没有宏替换） 的总长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="903fc-133">The total length of the file path, file mask, and file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="903fc-134">（这是 MessageBox 数据库的限制）。</span><span class="sxs-lookup"><span data-stu-id="903fc-134">(This is a restriction of the MessageBox database.)</span></span>  
  
- <span data-ttu-id="903fc-135">文件路径不能以开头"`\\`？"。</span><span class="sxs-lookup"><span data-stu-id="903fc-135">The file path cannot begin with "`\\`?".</span></span>  
  
- <span data-ttu-id="903fc-136">不能在文件路径中，使用网络映射的驱动器号，因为它们是基于用户会话。</span><span class="sxs-lookup"><span data-stu-id="903fc-136">Mapped network drive letters cannot be used in the file path, because they are user session based.</span></span>  
  
  <span data-ttu-id="903fc-137">BizTalk 消息引擎始终会验证文件名和文件掩码属性在设计时通过使用前面列出的项。</span><span class="sxs-lookup"><span data-stu-id="903fc-137">The BizTalk Messaging Engine always validates the file name and file mask properties at design time by using the items previously listed.</span></span> <span data-ttu-id="903fc-138">此外，文件适配器验证文件名和文件掩码属性在运行时如果适配器在动态端口上发送消息。</span><span class="sxs-lookup"><span data-stu-id="903fc-138">In addition, the File adapter validates the file name and file mask properties at run time if the adapter sends the message on a dynamic port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="903fc-139">文件适配器不提取系统文件或只读文件。</span><span class="sxs-lookup"><span data-stu-id="903fc-139">The File adapter does not pick up system files or read-only files.</span></span> <span data-ttu-id="903fc-140">将选择仅基于磁盘的文件，而不是设备文件。</span><span class="sxs-lookup"><span data-stu-id="903fc-140">Only disk-based files are picked up, and not device files.</span></span>  

## <a name="using-macros-in-file-names"></a><span data-ttu-id="903fc-141">在文件名称中使用宏</span><span class="sxs-lookup"><span data-stu-id="903fc-141">Using macros in file names</span></span>

<span data-ttu-id="903fc-142">可以使用一组预定义的宏来动态创建的文件发送处理程序在其中写入消息文件。</span><span class="sxs-lookup"><span data-stu-id="903fc-142">You can use a predefined set of macros to dynamically create the files in which the File send handler writes messages.</span></span> <span data-ttu-id="903fc-143">然后再创建文件系统上的文件，文件发送处理程序替换所有宏使用单独的值在文件名中。</span><span class="sxs-lookup"><span data-stu-id="903fc-143">Before creating a file on the file system, the File send handler replaces all the macros in the file name with their individual values.</span></span> <span data-ttu-id="903fc-144">可以在一个文件名中使用多个不同的宏。</span><span class="sxs-lookup"><span data-stu-id="903fc-144">You can use several different macros in one file name.</span></span>  
  
 <span data-ttu-id="903fc-145">配置文件发送处理程序使用 BizTalk 浏览器对象模型时，可以使用文件名宏。</span><span class="sxs-lookup"><span data-stu-id="903fc-145">You can use the file name macros while configuring the File send handler using the BizTalk Explorer object model.</span></span>  
  
 <span data-ttu-id="903fc-146">文件发送处理程序不会使用值替换宏，如果以下任何条件成立：</span><span class="sxs-lookup"><span data-stu-id="903fc-146">The File send handler does not replace the macros with a value if any of the following are true:</span></span>  
  
- <span data-ttu-id="903fc-147">未设置相应的系统属性。</span><span class="sxs-lookup"><span data-stu-id="903fc-147">The corresponding system property is not set.</span></span>  
  
- <span data-ttu-id="903fc-148">宏拼写错误。</span><span class="sxs-lookup"><span data-stu-id="903fc-148">The macro is misspelled.</span></span>  
  
- <span data-ttu-id="903fc-149">该宏的值包含在文件名中无效的符号。</span><span class="sxs-lookup"><span data-stu-id="903fc-149">The value for the macro contains symbols that are not valid in the file name.</span></span>  
  
  <span data-ttu-id="903fc-150">如果出现下列任一条件，文件发送处理程序将保留在文件名称不变，例如 Myfile_%MessageID%.xml 宏。</span><span class="sxs-lookup"><span data-stu-id="903fc-150">If any of these conditions occur, the File send handler leaves the macros in the file name untouched, for example Myfile_%MessageID%.xml.</span></span>  
  
  <span data-ttu-id="903fc-151">下表列出了受支持的宏，并介绍文件发送处理程序如何替换它们。</span><span class="sxs-lookup"><span data-stu-id="903fc-151">The following table lists the supported macros and describes how the File send handler replaces them.</span></span>  
  
|<span data-ttu-id="903fc-152">宏名</span><span class="sxs-lookup"><span data-stu-id="903fc-152">Macro name</span></span>|<span data-ttu-id="903fc-153">替换值</span><span class="sxs-lookup"><span data-stu-id="903fc-153">Substitute value</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="903fc-154">%datetime%</span><span class="sxs-lookup"><span data-stu-id="903fc-154">%datetime%</span></span>|<span data-ttu-id="903fc-155">协调世界时 (UTC) 日期时间格式 YYYY MM DDThhmmss (例如，1997年-07-12T103508)。</span><span class="sxs-lookup"><span data-stu-id="903fc-155">Coordinated Universal Time (UTC) date time in the format YYYY-MM-DDThhmmss (for example, 1997-07-12T103508).</span></span>|  
|<span data-ttu-id="903fc-156">%datetime_bts2000%</span><span class="sxs-lookup"><span data-stu-id="903fc-156">%datetime_bts2000%</span></span>|<span data-ttu-id="903fc-157">YYYYMMDDhhmmsss 格式的 UTC 日期时间，其中，sss 表示秒和毫秒（例如，199707121035234 表示 1997/07/12 10:35:23 和 400 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="903fc-157">UTC date time in the format YYYYMMDDhhmmsss, where sss means seconds and milliseconds (for example, 199707121035234 means 1997/07/12, 10:35:23 and 400 milliseconds).</span></span>|  
|<span data-ttu-id="903fc-158">%datetime.tz%</span><span class="sxs-lookup"><span data-stu-id="903fc-158">%datetime.tz%</span></span>|<span data-ttu-id="903fc-159">本地日期时间加上 GMT 时区，格式为 YYYY-MM-DDThhmmssTZD（例如 1997-07-12T103508+800）。</span><span class="sxs-lookup"><span data-stu-id="903fc-159">Local date time plus time zone from GMT in the format YYYY-MM-DDThhmmssTZD, (for example, 1997-07-12T103508+800).</span></span>|  
|<span data-ttu-id="903fc-160">%DestinationParty%</span><span class="sxs-lookup"><span data-stu-id="903fc-160">%DestinationParty%</span></span>|<span data-ttu-id="903fc-161">目标参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-161">Name of the destination party.</span></span> <span data-ttu-id="903fc-162">该值来自消息上下文属性 **BTS.DestinationParty**。</span><span class="sxs-lookup"><span data-stu-id="903fc-162">The value comes from the message context property **BTS.DestinationParty**.</span></span>|  
|<span data-ttu-id="903fc-163">%DestinationPartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="903fc-163">%DestinationPartyQualifier%</span></span>|<span data-ttu-id="903fc-164">目标参与方的限定符。</span><span class="sxs-lookup"><span data-stu-id="903fc-164">Qualifier of the destination party.</span></span> <span data-ttu-id="903fc-165">该值来自消息上下文属性 **BTS.DestinationPartyQualifier**。</span><span class="sxs-lookup"><span data-stu-id="903fc-165">The value comes from the message context property **BTS.DestinationPartyQualifier**.</span></span>|  
|<span data-ttu-id="903fc-166">%MessageID%</span><span class="sxs-lookup"><span data-stu-id="903fc-166">%MessageID%</span></span>|<span data-ttu-id="903fc-167">BizTalk Server 中消息的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="903fc-167">Globally unique identifier (GUID) of the message in BizTalk Server.</span></span> <span data-ttu-id="903fc-168">该值直接来自消息上下文属性**BTS。MessageID**。</span><span class="sxs-lookup"><span data-stu-id="903fc-168">The value comes directly from the message context property **BTS.MessageID**.</span></span>|  
|<span data-ttu-id="903fc-169">%SourceFileName%</span><span class="sxs-lookup"><span data-stu-id="903fc-169">%SourceFileName%</span></span>|<span data-ttu-id="903fc-170">文件适配器从中读取消息的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-170">Name of the file from which the File adapter read the message.</span></span> <span data-ttu-id="903fc-171">文件名包括扩展和排除的文件路径，例如 Sample.xml。</span><span class="sxs-lookup"><span data-stu-id="903fc-171">The file name includes the extension and excludes the file path, for example, Sample.xml.</span></span> <span data-ttu-id="903fc-172">文件适配器在替代此属性，从存储中的绝对文件路径提取文件名**文件。ReceivedFileName**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="903fc-172">When substituting this property, the File adapter extracts the file name from the absolute file path stored in the **FILE.ReceivedFileName** context property.</span></span> <span data-ttu-id="903fc-173">如果上下文属性的值 — 例如，如果文件适配器之外的适配器上接收的消息 — 宏将不进行替换，并将保持原样的文件名称中 (例如，C:\Drop\\%sourcefilename%)。</span><span class="sxs-lookup"><span data-stu-id="903fc-173">If the context property does not have a value—for example, if a message was received on an adapter other than the File adapter—the macro will not be substituted and will remain in the file name as is (for example, C:\Drop\\%SourceFileName%).</span></span> <span data-ttu-id="903fc-174">**注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。</span><span class="sxs-lookup"><span data-stu-id="903fc-174">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="903fc-175">%SourceParty%</span><span class="sxs-lookup"><span data-stu-id="903fc-175">%SourceParty%</span></span>|<span data-ttu-id="903fc-176">文件适配器从其接收消息的源参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="903fc-176">Name of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="903fc-177">**注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。</span><span class="sxs-lookup"><span data-stu-id="903fc-177">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="903fc-178">%SourcePartyQualifier%</span><span class="sxs-lookup"><span data-stu-id="903fc-178">%SourcePartyQualifier%</span></span>|<span data-ttu-id="903fc-179">文件适配器从其接收消息的源参与方的限定符。</span><span class="sxs-lookup"><span data-stu-id="903fc-179">Qualifier of the source party from which the File adapter received the message.</span></span> <span data-ttu-id="903fc-180">**注意：** 此宏的正确实现需要输出消息为收到的消息的消息相同。</span><span class="sxs-lookup"><span data-stu-id="903fc-180">**Note:**  Correct implementation of this macro requires that the output message is the same message as the received message.</span></span>|  
|<span data-ttu-id="903fc-181">%time%</span><span class="sxs-lookup"><span data-stu-id="903fc-181">%time%</span></span>|<span data-ttu-id="903fc-182">hhmmss 格式的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="903fc-182">UTC time in the format hhmmss.</span></span>|  
|<span data-ttu-id="903fc-183">%time.tz%</span><span class="sxs-lookup"><span data-stu-id="903fc-183">%time.tz%</span></span>|<span data-ttu-id="903fc-184">本地时间加上 GMT 时区，格式为 hhmmssTZD（例如 124525+530）。</span><span class="sxs-lookup"><span data-stu-id="903fc-184">Local time plus time zone from GMT in the format hhmmssTZD (for example, 124525+530).</span></span>|  
  
 
## <a name="receive-folder-and-destination-location-properties-gotchas"></a><span data-ttu-id="903fc-185">接收文件夹和目标位置属性难题</span><span class="sxs-lookup"><span data-stu-id="903fc-185">Receive folder and destination location properties gotchas</span></span>

<span data-ttu-id="903fc-186">File 接收位置是一个字符串，包含文件系统上的文件夹的路径或网络共享的文件接收处理程序读取文件。</span><span class="sxs-lookup"><span data-stu-id="903fc-186">The file receive location is a string that contains a path to a folder on a file system or network share from which the File receive handler reads files.</span></span> <span data-ttu-id="903fc-187">文件目标位置是一个字符串，包含文件系统上的文件夹的路径或网络共享，文件发送处理程序会将文件写入。</span><span class="sxs-lookup"><span data-stu-id="903fc-187">The file destination location is a string that contains a path to a folder on a file system or network share where the File send handler writes files.</span></span>  
  
 <span data-ttu-id="903fc-188">以下限制适用于接收文件夹和目标位置属性：</span><span class="sxs-lookup"><span data-stu-id="903fc-188">The following restrictions apply to the receive folder and destination location properties:</span></span>  
  
- <span data-ttu-id="903fc-189">当用户在指定属性时则不需要的文件系统或网络共享上的文件路径存在。</span><span class="sxs-lookup"><span data-stu-id="903fc-189">Existence of the file path on a file system or network share is not required at the time when you specify the property in the user.</span></span>  
  
- <span data-ttu-id="903fc-190">必须始终为绝对文件路径。</span><span class="sxs-lookup"><span data-stu-id="903fc-190">The file path must always be absolute.</span></span>  
  
- <span data-ttu-id="903fc-191">可以通过使用通用命名约定 (UNC) 格式指定的文件路径 (例如， \\ \\ < *server* \> \\ < *共享*\>)。</span><span class="sxs-lookup"><span data-stu-id="903fc-191">You can specify the file path by using Universal Naming Convention (UNC) format (for example, \\\\<*server*\>\\<*share*\>).</span></span>  
  
- <span data-ttu-id="903fc-192">如果文件路径采用 UNC 格式，服务器名称不得包含以下字符: ' ~ ！</span><span class="sxs-lookup"><span data-stu-id="903fc-192">If the file path is in UNC format, the server name must not contain the following characters: \` ~ !</span></span> <span data-ttu-id="903fc-193">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span><span class="sxs-lookup"><span data-stu-id="903fc-193">@ # $ ^ & \* ( ) = + [ ] { } \ &#124; ; : ' " , \< \> / ?</span></span> <span data-ttu-id="903fc-194">;</span><span class="sxs-lookup"><span data-stu-id="903fc-194">;</span></span>  
  
- <span data-ttu-id="903fc-195">不能使用父 (\\...\\) 和当前 (\\。\\) 文件夹中的文件路径的任何部分的符号。</span><span class="sxs-lookup"><span data-stu-id="903fc-195">You cannot use parent (\\..\\) and current (\\.\\) folder symbols in any part of the file path.</span></span>  
  
- <span data-ttu-id="903fc-196">文件路径不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="903fc-196">The file path is not case-sensitive.</span></span>  
  
- <span data-ttu-id="903fc-197">文件路径不能包含任何以下字符： \< \> : / &#124; "？</span><span class="sxs-lookup"><span data-stu-id="903fc-197">The file path cannot contain any of the following characters: \< \> : / &#124; " ?</span></span> <span data-ttu-id="903fc-198">\* ;</span><span class="sxs-lookup"><span data-stu-id="903fc-198">\* ;</span></span>  
  
- <span data-ttu-id="903fc-199">不能在文件路径中使用以下保留的设备名称：CON、 PRN、 AUX、 时钟 $、 NUL、 COM1、 COM2、 COM3、 COM4、 COM5、 COM6、 COM7、 COM8、 COM9、 LPT1、 LPT2、 LPT3、 LPT4、 LPT5、 LPT6、 LPT7、 LPT8 和 LPT9。</span><span class="sxs-lookup"><span data-stu-id="903fc-199">You cannot use the following reserved device names in the file path: CON, PRN, AUX, CLOCK$, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.</span></span>  
  
- <span data-ttu-id="903fc-200">文件路径、 文件掩码或文件名 （没有宏替换） 的总长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="903fc-200">Total length of file path, file mask, or file name (without macro substitution) must not exceed 256 characters.</span></span> <span data-ttu-id="903fc-201">（MessageBox 数据库规定了此限制。）</span><span class="sxs-lookup"><span data-stu-id="903fc-201">(The MessageBox database imposes this restriction.)</span></span>  
  
- <span data-ttu-id="903fc-202">文件适配器不支持 Unicode 规范的文件路径 (例如，"\\\\？\\")。</span><span class="sxs-lookup"><span data-stu-id="903fc-202">The File adapter does not support Unicode specification of the file path (for example, "\\\\?\\").</span></span>  
  
  <span data-ttu-id="903fc-203">对接收文件夹属性的限制：</span><span class="sxs-lookup"><span data-stu-id="903fc-203">Restrictions on the receive folder property only:</span></span>  
  
- <span data-ttu-id="903fc-204">未设置接收文件夹属性为使用 Microsoft Windows NT 分布式文件系统的带符号链接的文件夹。</span><span class="sxs-lookup"><span data-stu-id="903fc-204">Do not set the receive folder property to a folder that uses the Microsoft Windows NT Distributed File System with a symbolic link.</span></span> <span data-ttu-id="903fc-205">如果使用的 Windows NT 分布式文件系统，则可以仅使用文件夹具有直接网络路径在文件适配器接收位置。</span><span class="sxs-lookup"><span data-stu-id="903fc-205">If you are using Windows NT Distributed File System, you can only use folders with straight network paths in File adapter receive locations.</span></span>  
  
- <span data-ttu-id="903fc-206">文档发送到 UNC 路径时，你有多个服务器接收文件适配器的接收位置的文档时，只有一台服务器将选取并处理的大多数文档发送到该 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="903fc-206">When documents are sent to a UNC path, and you have more than one server receiving documents at the receive location for the File adapter, only one server will pick up and process most of the documents sent to that UNC path.</span></span> <span data-ttu-id="903fc-207">有关文件重命名的详细信息，请参阅文件接收适配器的一部分[文件适配器](../core/file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="903fc-207">For more information about file renaming, see the File Receive Adapter section of [File Adapter](../core/file-adapter.md).</span></span>  
  
  <span data-ttu-id="903fc-208">限制只发送文件夹属性：</span><span class="sxs-lookup"><span data-stu-id="903fc-208">Restrictions on the send folder property only:</span></span>  
  
- <span data-ttu-id="903fc-209">文件适配器可能没有足够的操作系统资源来同时处理所有批中消息的 Microsoft Windows Vista 等非服务器操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="903fc-209">The file adapter may not have enough operating system resources to process all of the messages in a batch concurrently when running on a non-server operating system like Microsoft Windows Vista.</span></span>  
  
  <span data-ttu-id="903fc-210">文件适配器在设计时通过使用前面所述的规则来验证文件路径。</span><span class="sxs-lookup"><span data-stu-id="903fc-210">The File adapter validates the file path at design time by using the previously mentioned rules.</span></span> <span data-ttu-id="903fc-211">此外，文件适配器验证消息在运行时如果适配器使用文件适配器通过动态端口发送消息。</span><span class="sxs-lookup"><span data-stu-id="903fc-211">In addition, the File adapter validates the message at run time if the adapter sends the message through a dynamic port with a File adapter.</span></span>  
  
