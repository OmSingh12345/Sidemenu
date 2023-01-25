# Sidemenu
KyDrawerSideMenu Using Pod

in Login Screeen ,On login Button call the moveToHome() function ,and navigate from main to Home in Swift ,and implement the Designning part on home screen 

---------> used this extension in login screen and Follow Step by Step
extension UIViewController{
    func moveToHome(){
        let drawer = KYDrawerController.init(drawerDirection: .left, drawerWidth:UIScreen.main.bounds.width - 80)
        let initialViewController = UIStoryboard(name: "Home", bundle: .main).instantiateViewController(withIdentifier: "HomeViewController") as! HomeViewController
      //  initialViewController.selectedIndex = index
        let nav1 = UINavigationController.init(rootViewController: initialViewController)
        nav1.isNavigationBarHidden = true
        drawer.mainViewController = nav1
        let drawerController = UIStoryboard(name: "Home", bundle: .main).instantiateViewController(withIdentifier: "SidemenuVc") as! SidemenuVc
        let nav2 =  UINavigationController(rootViewController: drawerController)
        nav2.isNavigationBarHidden = true
        drawer.drawerViewController = nav2
        UIApplication.shared.windows.first?.rootViewController = drawer
        UIApplication.shared.windows.first?.makeKeyAndVisible()
    }
}
