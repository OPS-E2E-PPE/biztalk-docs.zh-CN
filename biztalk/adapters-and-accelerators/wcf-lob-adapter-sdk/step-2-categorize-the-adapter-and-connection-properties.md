---
title: 步骤 2： 对其进行分类的适配器和连接属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45b3dc64-2078-4008-878b-501f727f4a11
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e9d49323695b1070a8065cf7a5e548e61fc5db9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226821"
---
# <a name="step-2-categorize-the-adapter-and-connection-properties"></a><span data-ttu-id="496c2-102">步骤 2： 对其进行分类的适配器和连接属性</span><span class="sxs-lookup"><span data-stu-id="496c2-102">Step 2: Categorize the Adapter and Connection Properties</span></span>
<span data-ttu-id="496c2-103">![步骤 2 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="496c2-103">![Step 2 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="496c2-104">**完成时间：** 30 分钟</span><span class="sxs-lookup"><span data-stu-id="496c2-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="496c2-105">在此步骤中，您将更新**EchoAdapterBindingElement**和**EchoAdapterBindingElementExtensionElement**要分配给适配器和连接属性的类别的类。</span><span class="sxs-lookup"><span data-stu-id="496c2-105">In this step, you update the **EchoAdapterBindingElement** and **EchoAdapterBindingElementExtensionElement** classes to assign a category to your adapter and connection properties.</span></span> <span data-ttu-id="496c2-106">通过这样做，属性按逻辑分组在中按类别[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="496c2-106">By doing so, properties are logically grouped by category in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools.</span></span> <span data-ttu-id="496c2-107">例如，如果你想**应用程序**， **EnableAuthentication**，和**主机名**属性以便在下显示**连接**类别如下所示，你需要将连接类别分配给每个应用程序、 EnableAuthentication 和主机名的属性。</span><span class="sxs-lookup"><span data-stu-id="496c2-107">For example, if you want the **Application**, **EnableAuthentication**, and **Hostname** properties to appear under the **Connection** category as shown below, you need to assign the Connection category to each of the Application, EnableAuthentication, and Hostname properties.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c7c0c013-6651-4c32-9f8b-b546a68a0267.gif "c7c0c013-6651-4c32-9f8b-b546a68a0267")  
  
 <span data-ttu-id="496c2-108">同样，如果你想**InboundFileFilter**和**InboundFleSystemWatcherFolder**属性以便在下显示**入站**类别如下所示，你需要将入站的类别分配给每个。</span><span class="sxs-lookup"><span data-stu-id="496c2-108">Similarly, if you want the **InboundFileFilter** and **InboundFleSystemWatcherFolder** properties to appear under the **Inbound** category as shown below, you need to assign the Inbound category to each.</span></span> <span data-ttu-id="496c2-109">如果你想**计数**和**EnableConnectionPooling**以便在下显示**杂项**类别中，你需要将杂项类别分配给每个。</span><span class="sxs-lookup"><span data-stu-id="496c2-109">If you want **Count** and **EnableConnectionPooling** to appear under the **Misc** category, you need to assign the Misc category to each.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2acb7677-8b50-4e45-96a3-42d0e2011f19.gif "2acb7677-8b50-4e45-96a3-42d0e2011f19")  
  
 <span data-ttu-id="496c2-110">请记住，你可以分配你选择的任何类别名称的属性。</span><span class="sxs-lookup"><span data-stu-id="496c2-110">Keep in mind that you can assign a property with any category name you choose.</span></span> <span data-ttu-id="496c2-111">在此示例中，由于 EnableConnnectionPooling 属性不属于任何其他类别中，我们将其分类为杂项 （杂项）。</span><span class="sxs-lookup"><span data-stu-id="496c2-111">In this example, since the EnableConnnectionPooling property does not belong to any other categories, we categorize it as Misc (Miscellaneous).</span></span> <span data-ttu-id="496c2-112">有关 InboundFileFilter 属性，因为在此示例中，在入站处理期间使用它很将入站分配给属性，而不是杂项更为合适。</span><span class="sxs-lookup"><span data-stu-id="496c2-112">As to the InboundFileFilter property, since it is used during the inbound handling within the example, it is more appropriate to assign Inbound to the property, rather than Miscellaneous.</span></span> <span data-ttu-id="496c2-113">下面是为 echo 适配器完成自定义属性进行分类。</span><span class="sxs-lookup"><span data-stu-id="496c2-113">Here is the complete custom property categorization for the echo adapter.</span></span>  
  
|<span data-ttu-id="496c2-114">**属性**</span><span class="sxs-lookup"><span data-stu-id="496c2-114">**Property**</span></span>|<span data-ttu-id="496c2-115">**类别**</span><span class="sxs-lookup"><span data-stu-id="496c2-115">**Category**</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="496c2-116">InboundFileFilter</span><span class="sxs-lookup"><span data-stu-id="496c2-116">InboundFileFilter</span></span>|<span data-ttu-id="496c2-117">入站</span><span class="sxs-lookup"><span data-stu-id="496c2-117">Inbound</span></span>|  
|<span data-ttu-id="496c2-118">InboundFileSystemWatcherFolder</span><span class="sxs-lookup"><span data-stu-id="496c2-118">InboundFileSystemWatcherFolder</span></span>|<span data-ttu-id="496c2-119">入站</span><span class="sxs-lookup"><span data-stu-id="496c2-119">Inbound</span></span>|  
|<span data-ttu-id="496c2-120">Count</span><span class="sxs-lookup"><span data-stu-id="496c2-120">Count</span></span>|<span data-ttu-id="496c2-121">杂项</span><span class="sxs-lookup"><span data-stu-id="496c2-121">Misc</span></span>|  
|<span data-ttu-id="496c2-122">EnableConnectionPooling</span><span class="sxs-lookup"><span data-stu-id="496c2-122">EnableConnectionPooling</span></span>|<span data-ttu-id="496c2-123">杂项</span><span class="sxs-lookup"><span data-stu-id="496c2-123">Misc</span></span>|  
|<span data-ttu-id="496c2-124">应用程序</span><span class="sxs-lookup"><span data-stu-id="496c2-124">Application</span></span>|<span data-ttu-id="496c2-125">连接</span><span class="sxs-lookup"><span data-stu-id="496c2-125">Connection</span></span>|  
|<span data-ttu-id="496c2-126">EnableAuthentication</span><span class="sxs-lookup"><span data-stu-id="496c2-126">EnableAuthentication</span></span>|<span data-ttu-id="496c2-127">连接</span><span class="sxs-lookup"><span data-stu-id="496c2-127">Connection</span></span>|  
|<span data-ttu-id="496c2-128">Hostname</span><span class="sxs-lookup"><span data-stu-id="496c2-128">Hostname</span></span>|<span data-ttu-id="496c2-129">连接</span><span class="sxs-lookup"><span data-stu-id="496c2-129">Connection</span></span>|  
|<span data-ttu-id="496c2-130">EchoInUpperCase</span><span class="sxs-lookup"><span data-stu-id="496c2-130">EchoInUpperCase</span></span>|<span data-ttu-id="496c2-131">格式</span><span class="sxs-lookup"><span data-stu-id="496c2-131">Format</span></span>|  
  
 <span data-ttu-id="496c2-132">除了这些更改，你还修改的 Dispose 方法**EchoAdapterHandlerBase**。</span><span class="sxs-lookup"><span data-stu-id="496c2-132">In addition to those changes, you also modify the Dispose method of **EchoAdapterHandlerBase**.</span></span>  
  
 <span data-ttu-id="496c2-133">有关由 echo 适配器中，公开了适配器属性，请参阅的适配器属性部分[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="496c2-133">For the adapter properties exposed by the echo adapter, see the adapter properties section of the [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="496c2-134">先决条件</span><span class="sxs-lookup"><span data-stu-id="496c2-134">Prerequisites</span></span>  
 <span data-ttu-id="496c2-135">在开始此步骤之前，必须完成[步骤 1： 使用 WCF LOB 适配器开发向导创建 Echo 适配器项目](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="496c2-135">Before you begin this step, you must complete [Step 1: Use the WCF LOB Adapter Development Wizard to Create the Echo Adapter Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-wcf-lob-adapter-development-wizard-to-create-the-echo-adapter.md).</span></span> <span data-ttu-id="496c2-136">你还应熟悉`System.ServiceModel.Configuration.BindingElementExtensionElement`和`System.ServiceModel.Configuration.StandardBindingElement`类。</span><span class="sxs-lookup"><span data-stu-id="496c2-136">You should also be familiar with the `System.ServiceModel.Configuration.BindingElementExtensionElement` and `System.ServiceModel.Configuration.StandardBindingElement` classes.</span></span>  
  
## <a name="update-the-echoadapterhandlerbase-dispose-method"></a><span data-ttu-id="496c2-137">更新 EchoAdapterHandlerBase Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="496c2-137">Update the EchoAdapterHandlerBase Dispose method</span></span>  
  
1.  <span data-ttu-id="496c2-138">在**解决方案资源管理器**，双击**EchoAdapterHandlerBase.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="496c2-138">In **Solution Explorer**, double-click the **EchoAdapterHandlerBase.cs** file.</span></span>  
  
2.  <span data-ttu-id="496c2-139">删除以下语句从**释放**方法：</span><span class="sxs-lookup"><span data-stu-id="496c2-139">Remove the following statement from the **Dispose** method:</span></span>  
  
    ```csharp  
    throw new NotImplementedException("The method or operation is not implemented.");  
    ```  
  
     <span data-ttu-id="496c2-140">修改后的方法应类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="496c2-140">The revised method should look similar to the following:</span></span>  
  
    ```csharp  
    protected virtual void Dispose(bool disposing)  
    {  
       //  
       //TODO: Implement Dispose. Override this method in respective Handler classes  
       //  
    }  
    ```  
  
## <a name="update-the-adapter-properties-class"></a><span data-ttu-id="496c2-141">更新适配器属性类</span><span class="sxs-lookup"><span data-stu-id="496c2-141">Update the Adapter properties class</span></span>  
  
1.  <span data-ttu-id="496c2-142">在**解决方案资源管理器**，双击**EchoAdapterBindingElement.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="496c2-142">In **Solution Explorer**, double-click the **EchoAdapterBindingElement.cs** file.</span></span>  
  
2.  <span data-ttu-id="496c2-143">在 Visual Studio 编辑器中，展开**自定义生成属性**区域。</span><span class="sxs-lookup"><span data-stu-id="496c2-143">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="496c2-144">若要将分配**杂项**类别与**计数**属性，将下面的单个语句添加到的开头**计数**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-144">To assign the **Misc** category to the **Count** property, add the following single statement to the beginning of the **Count** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
     <span data-ttu-id="496c2-145">**计数**实现现在应匹配以下内容：</span><span class="sxs-lookup"><span data-stu-id="496c2-145">The **Count** implementation should now match the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="496c2-146">若要将分配**杂项**类别与**EnableConnectionPooling**属性，将下面的单个语句添加到的开头**EnableConnectionPooling**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-146">To assign the **Misc** category to the **EnableConnectionPooling** property, add the following single statement to the beginning of the **EnableConnectionPooling** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    ```  
  
5.  <span data-ttu-id="496c2-147">若要将分配**入站**类别与**InboundFileFilter**属性，将下面的单个语句添加到的开头**InboundFileFilter**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-147">To assign the **Inbound** category to the **InboundFileFilter** property, add the following single statement to the beginning of the **InboundFileFilter** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
6.  <span data-ttu-id="496c2-148">若要将分配**入站**categoryto **inboundFleSystemWatcherFolder**属性，将下面的单个语句添加到的开头**inboundFleSystemWatcherFolder**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-148">To assign the **Inbound** categoryto **inboundFleSystemWatcherFolder** property, add the following single statement to the beginning of the **inboundFleSystemWatcherFolder** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Inbound")]  
    ```  
  
7.  <span data-ttu-id="496c2-149">检查以确保中的代码**自定义生成属性**区域匹配以下：</span><span class="sxs-lookup"><span data-stu-id="496c2-149">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("count", DefaultValue = 5)]  
    public int Count  
    {  
        get  
        {  
            return ((int)(base["Count"]));  
        }  
        set  
        {  
            base["Count"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("")]  
    [System.Configuration.ConfigurationProperty("enableConnectionPooling", DefaultValue = true)]  
    public bool EnableConnectionPooling  
    {  
        get  
        {  
            return ((bool)(base["EnableConnectionPooling"]));  
        }  
        set  
        {  
            base["EnableConnectionPooling"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileFilter", DefaultValue = "*.txt")]  
    public string InboundFileFilter  
    {  
        get  
        {  
            return ((string)(base["InboundFileFilter"]));  
        }  
        set  
        {  
            base["InboundFileFilter"] = value;  
        }  
    }  
  
    [System.ComponentModel.Category("Inbound")]  
    [System.Configuration.ConfigurationProperty("inboundFileSystemWatcherFolder", DefaultValue = "{InboundFileSystemWatcherFolder}")]  
    public string InboundFileSystemWatcherFolder  
    {  
        get  
        {  
            return ((string)(base["InboundFileSystemWatcherFolder"]));  
        }  
        set  
        {  
            base["InboundFileSystemWatcherFolder"] = value;  
        }  
    }  
  
    #endregion Custom Generated Properties  
    ```  
  
## <a name="update-the-connection-properties"></a><span data-ttu-id="496c2-150">更新连接属性</span><span class="sxs-lookup"><span data-stu-id="496c2-150">Update the Connection Properties</span></span>  
  
1.  <span data-ttu-id="496c2-151">在**解决方案资源管理器**，双击**EchoAdapterConnectionUri.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="496c2-151">In **Solution Explorer**, double-click the **EchoAdapterConnectionUri.cs** file.</span></span>  
  
2.  <span data-ttu-id="496c2-152">在 Visual Studio 编辑器中，展开**自定义生成属性**区域。</span><span class="sxs-lookup"><span data-stu-id="496c2-152">In the Visual Studio editor, expand the **Custom Generated Properties** region.</span></span>  
  
3.  <span data-ttu-id="496c2-153">若要将分配**格式**类别与**EchoInUpperCase**属性，将下面的单个语句添加到的开头**EchoInUpperCase**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-153">To assign the **Format** category to the **EchoInUpperCase** property, add the following single statement to the beginning of the **EchoInUpperCase** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Format")]  
    ```  
  
4.  <span data-ttu-id="496c2-154">若要将分配**连接**类别与**主机名**属性，将下面的单个语句添加到的开头**主机名**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-154">To assign the **Connection** category to the **Hostname** property, add the following single statement to the beginning of the **Hostname** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
5.  <span data-ttu-id="496c2-155">若要将分配**连接**类别与**应用程序**属性，将下面的单个语句添加到的开头**应用程序**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-155">To assign the **Connection** category to the **Application** property, add the following single statement to the beginning of the **Application** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
6.  <span data-ttu-id="496c2-156">若要将分配**连接**categoryto **EnableAuthentication**属性，将下面的单个语句添加到的开头**EnableAuthentication**实现。</span><span class="sxs-lookup"><span data-stu-id="496c2-156">To assign the **Connection** categoryto **EnableAuthentication** property, add the following single statement to the beginning of the **EnableAuthentication** implementation.</span></span>  
  
    ```csharp  
    [System.ComponentModel.Category("Connection")]  
    ```  
  
7.  <span data-ttu-id="496c2-157">检查以确保中的代码**自定义生成属性**区域匹配以下：</span><span class="sxs-lookup"><span data-stu-id="496c2-157">Check to ensure that the code in the **Custom Generated Properties** region matches the following:</span></span>  
  
    ```csharp  
    #region Custom Generated Properties  
            [System.ComponentModel.Category("Format")]  
            public bool EchoInUpperCase  
            {  
                get  
                {  
                    return this.echoInUpperCase;  
                }  
                set  
                {  
                    this.echoInUpperCase = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Hostname  
            {  
                get  
                {  
                    return this.hostname;  
                }  
                set  
                {  
                    this.hostname = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public string Application  
            {  
                get  
                {  
                    return this.application;  
                }  
                set  
                {  
                    this.application = value;  
                }  
            }  
  
            [System.ComponentModel.Category("Connection")]  
            public bool EnableAuthentication  
            {  
                get  
                {  
                    return this.enableAuthentication;  
                }  
                set  
                {  
                    this.enableAuthentication = value;  
                }  
            }  
            #endregion Custom Generated Properties  
    ```  
  
8.  <span data-ttu-id="496c2-158">在 Visual Studio 中，从**文件**菜单上，单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="496c2-158">In Visual Studio, from the **File** menu, click **Save All**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="496c2-159">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="496c2-159">You saved your work.</span></span> <span data-ttu-id="496c2-160">你可以安全地在此时关闭 Visual Studio 或转到下一步，[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="496c2-160">You can safely close Visual Studio at this time or go to the next step, [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="496c2-161">未我只需做什么？</span><span class="sxs-lookup"><span data-stu-id="496c2-161">What Did I Just Do?</span></span>  
 <span data-ttu-id="496c2-162">你刚刚更新了要分配给由 echo 适配器公开每个适配器和连接属性的类别的类。</span><span class="sxs-lookup"><span data-stu-id="496c2-162">You just updated classes to assign a category to each adapter and connection property exposed by the echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="496c2-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="496c2-163">Next Steps</span></span>  
 <span data-ttu-id="496c2-164">你实现连接、 元数据浏览、 搜索和解析功能和出站消息交换。</span><span class="sxs-lookup"><span data-stu-id="496c2-164">You implement connection, metadata browsing, searching, and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="496c2-165">最后，生成并部署 echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="496c2-165">Lastly, you build and deploy the echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="496c2-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="496c2-166">See Also</span></span>  
 <span data-ttu-id="496c2-167">[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="496c2-167">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="496c2-168">教程 1： 开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="496c2-168">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)