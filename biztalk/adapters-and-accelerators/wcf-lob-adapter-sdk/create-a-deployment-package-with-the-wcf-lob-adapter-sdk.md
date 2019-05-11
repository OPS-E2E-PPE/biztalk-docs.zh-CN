---
title: 使用 WCF LOB 适配器 SDK 创建部署包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10022981-7944-45d6-a78a-4d680a79b010
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6d8a74929d5a3f5073e2ac927d3959068166dc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363739"
---
# <a name="create-a-deployment-package-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="677dc-102">使用 WCF LOB 适配器 SDK 创建部署包</span><span class="sxs-lookup"><span data-stu-id="677dc-102">Create a deployment package with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="677dc-103">在开发周期中，可以生成、 调试和运行您在 Visual Studio 中的适配器。</span><span class="sxs-lookup"><span data-stu-id="677dc-103">During the development cycle, you can build, debug, and run your adapter within Visual Studio.</span></span> <span data-ttu-id="677dc-104">适配器解决方案的输出是一个 DLL 程序集。</span><span class="sxs-lookup"><span data-stu-id="677dc-104">The output of an adapter solution is a DLL assembly.</span></span> <span data-ttu-id="677dc-105">可以生成使用 Visual Studio IDE 适配器解决方案或使用 devenv.exe 脚本创建一个适配器程序集。</span><span class="sxs-lookup"><span data-stu-id="677dc-105">You can build your adapter solution using Visual Studio IDE or use the devenv.exe scripts to create an adapter assembly.</span></span> <span data-ttu-id="677dc-106">一旦开发了适配器，并且它是供适配器使用者的环境中使用，必须创建允许适配器在测试和生产环境中安装的部署包。</span><span class="sxs-lookup"><span data-stu-id="677dc-106">Once the adapter is developed and it is ready for use within the adapter consumer's environment, you must create a deployment package that allows the adapter to be installed in test and production environments.</span></span>  
  
 <span data-ttu-id="677dc-107">可以包括在解决方案中的 Visual Studio 安装程序和部署项目。</span><span class="sxs-lookup"><span data-stu-id="677dc-107">You can include a Visual Studio Setup and Deployment project within the solution.</span></span> <span data-ttu-id="677dc-108">这可以用于自动生成的.msi 文件作为解决方案生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="677dc-108">This can be used to automatically generate an .msi file as part of the solution build.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="677dc-109">可以生成每次通过排除它通过配置管理器 （在生成菜单） Visual Studio.NET 中，在本地工作站生成解决方案时阻止安装和部署项目。</span><span class="sxs-lookup"><span data-stu-id="677dc-109">You can prevent the Setup and Deployment project from building each time you build the solution on your local workstation by excluding it through the Configuration Manager (on the Build menu) within Visual Studio .NET.</span></span> <span data-ttu-id="677dc-110">如果从使用此方法的解决方案生成中排除项目，不会影响源代码控制的解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="677dc-110">If you exclude a project from a solution build using this method, you do not affect the source controlled solution file.</span></span> <span data-ttu-id="677dc-111">解决方案用户选项文件的说明进行操作，这是特定于开发人员的和不受源代码管理中维护的更改。</span><span class="sxs-lookup"><span data-stu-id="677dc-111">Changes are maintained within the solution user option file, which is developer-specific and not under source control.</span></span>  
  
 <span data-ttu-id="677dc-112">每当新项目添加到你的解决方案时，您必须记得更新和配置部署项目，以确保新项目的输出是包含在.msi 文件并执行任何特定于项目的安装步骤。</span><span class="sxs-lookup"><span data-stu-id="677dc-112">Whenever new projects are added to your solution you must remember to update and configure the deployment project to ensure that the output of the new project is included within the .msi file and that any project-specific installation steps are performed.</span></span>  
  
 <span data-ttu-id="677dc-113">不足够，以只在用户计算机上安装适配器项目的输出。</span><span class="sxs-lookup"><span data-stu-id="677dc-113">It is not enough to just install the output of the adapter project on the user's computer.</span></span> <span data-ttu-id="677dc-114">适配器需要安装在全局程序集缓存 (GAC) 中，machine.config 文件需要更新，以注册适配器[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="677dc-114">The adapter needs to be installed in global assembly cache (GAC) and the machine.config file needs to be updated to register the adapter with [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="677dc-115">下面是可用于注册或注销使用的适配器的示例自定义操作[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="677dc-115">Following is a sample custom action that can be used to register or unregister an adapter with [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel;  
using System.Configuration.Install;  
  
using System.Reflection;  
using System.ServiceModel.Configuration;  
using System.Diagnostics;  
using System.Configuration;  
  
namespace Microsoft.Adapters.Samples.EchoV2  
{  
    //Custom action to register the adapter with WCF configuration in machine.config   
  
    //<system.serviceModel>  
    //  <extensions>  
    //    <bindingElementExtensions>  
    //      <add name="{BINDINGELEM_NAME}" type="{BINDINGELEM_TYPE}, {Assembly Information}" />  
    //    </bindingElementExtensions>  
    //    <bindingExtensions>  
    //      <add name="{BINDING_NAME}" type="{BINDING_TYPE}, {Assembly Information}" />  
    //    </bindingExtensions>  
    //  </extensions>  
    //  <client>  
    //    <endpoint binding="{BINDING_NAME}" contract="IMetadataExchange" name="{BINDING_SCHEME}" />  
    //  </client>  
    //</system.serviceModel>  
  
    [RunInstaller(true)]  
    public partial class WCFLOBAdapterInstaller : Installer  
    {  
        private Assembly adapterAssembly;  
        private Type bindingSectionType;  
        private Type bindingElementExtensionType;  
        const string INSTALLER_PARM_INSTALLDIR = "INSTALLDIR";  
        const string BINDING_ASSEMBLY_NAME = "Microsoft.Adapters.Samples.EchoV2.EchoAdapter.dll";  
        const string BINDINGELEM_NAME = "echoAdapterV2";  
        const string BINDINGELEM_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement";  
        const string BINDING_NAME = "echoAdapterBindingV2";  
        const string BINDING_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement";  
        const string BINDING_SCHEME = "echov2";  
  
        /// <summary>  
        /// Constructor - initialize the components and register the event handlers  
        /// </summary>  
        public WCFLOBAdapterInstaller()  
        {  
            InitializeComponent();  
            this.AfterInstall += new InstallEventHandler(AfterInstallEventHandler);  
            this.BeforeUninstall += new InstallEventHandler(BeforeUninstallEventHandler);  
        }  
  
        /// <summary>  
        /// Add the WCF configuration information in machine.config when installing the adapter.  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void AfterInstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                Debug.Assert(this.Context != null, "Context of this installation is null.");  
                string path = this.Context.Parameters[INSTALLER_PARM_INSTALLDIR] + BINDING_ASSEMBLY_NAME;  
                adapterAssembly = Assembly.LoadFrom(path);  
                Debug.Assert(adapterAssembly != null, "Adapter assembly is null.");  
                bindingSectionType = adapterAssembly.GetType(BINDING_TYPE, true);  
                Debug.Assert(bindingSectionType != null, "Binding type is null.");  
                bindingElementExtensionType = adapterAssembly.GetType(BINDINGELEM_TYPE, true);  
                Debug.Assert(bindingElementExtensionType != null, "Binding element extension type is null.");  
                AddMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while adding adapter configuration information. " + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Registers the adapter with the WCF configuration  
        /// NOTE: The   
        /// </summary>  
        public void AddMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            // add <client><endpoint>               
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            if (sectionGroup != null)  
            {  
  
                bool channelEndpointElementExists = false;  
                // this call can throw an exception if there is problem   
                // loading endpoint configurations - e.g. each endpoint  
                // tries to load binding which in turn loads the DLL  
                ClientSection clientSection = sectionGroup.Client;  
                foreach (ChannelEndpointElement elem in clientSection.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        channelEndpointElementExists = true;  
                        break;  
                    }  
                }  
                if (!channelEndpointElementExists)  
                {  
                    Debug.WriteLine("Adding ChannelEndpointElement for : " + BINDING_NAME);  
                    ChannelEndpointElement elem = new ChannelEndpointElement();  
                    elem.Binding = BINDING_NAME;  
                    elem.Name = BINDING_SCHEME;  
                    elem.Contract = "IMetadataExchange";  
                    sectionGroup.Client.Endpoints.Add(elem);  
                    Debug.WriteLine("Added ChannelEndpointElement for : " + BINDING_NAME);  
                }  
  
                // add <bindingElementExtension>  
                if (!sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDINGELEM_NAME, bindingElementExtensionType.FullName + "," + bindingElementExtensionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingElementExtensions.Add(ext);  
                }  
  
                // add <bindingExtension>  
                if (!sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDING_NAME, bindingSectionType.FullName + "," + bindingSectionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingExtensions.Add(ext);  
                }  
  
                config.Save();  
            }  
            else throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
        }  
  
        /// <summary>  
        /// Remove the machine configuration information when uninstalling the adapter  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void BeforeUninstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                RemoveMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while removing adapter configuration information" + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Unregisters the adapter with WCF configuration  
        /// </summary>  
        public void RemoveMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            ChannelEndpointElement elemToRemove = null;  
            if (sectionGroup != null)  
            {  
                // Remove <client><endpoint>  
                foreach (ChannelEndpointElement elem in sectionGroup.Client.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        elemToRemove = elem;  
                        break;  
                    }  
                }  
                if (elemToRemove != null)  
                {  
                    Debug.WriteLine("Removing ChannelEndpointElement for : " + BINDING_NAME);  
                    sectionGroup.Client.Endpoints.Remove(elemToRemove);  
                    Debug.WriteLine("Removed ChannelEndpointElement for : " + BINDING_NAME);  
                }  
                // Remove <bindingExtension> for this adapter  
                if (sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    sectionGroup.Extensions.BindingExtensions.RemoveAt(BINDING_NAME);  
                }  
                // Remove <bindingElementExtension> for this adapter  
                if (sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    sectionGroup.Extensions.BindingElementExtensions.RemoveAt(BINDINGELEM_NAME);  
                }  
                config.Save();  
            }  
            else  
            {  
                throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
            }  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestAddConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.AfterInstallEventHandler(null, null);  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestRemoveConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.BeforeUninstallEventHandler(null, null);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="677dc-116">如果你想要了解与部署包的示例适配器，可以下载包含测试代码和安装脚本已完成的 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="677dc-116">If you want to explore a sample adapter with a deployment package, you can download a completed Echo Adapter including test code and installation script.</span></span> <span data-ttu-id="677dc-117">此示例是在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。</span><span class="sxs-lookup"><span data-stu-id="677dc-117">This sample is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="677dc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="677dc-118">See Also</span></span>  
 <span data-ttu-id="677dc-119">[部署适配器使用 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="677dc-119">[Deploy an adapter using the WCF LOB adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="677dc-120">取消部署适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="677dc-120">Undeploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/undeploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)