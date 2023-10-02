# IleriSeviyeSwiftHataAyiklama
Swift dilinde hatalar ve ayıklama (debugging) konusu oldukça önemlidir, çünkü kod geliştirme sürecinin ayrılmaz bir parçasıdır. İşte Swift dilinde hataların
nasıl işlendiğini ve ayıklamanın nasıl yapıldığını anlatan temel bilgiler:

Hata Türleri: Swift'te hatalar "Error" adlı bir protokolü uygulayan tipler tarafından temsil edilir. Bu, özel hata tipleri oluşturabileceğiniz anlamına gelir.
Örneğin, aşağıdaki gibi kendi özel hata tipinizi tanımlayabilirsiniz:
enum CustomError: Error {
    case someError
    case anotherError
}

Hata Fırlatma: Bir hata durumu ortaya çıktığında, throw ifadesini kullanarak hatayı fırlatabilirsiniz. Örneğin:
func divide(_ a: Int, by b: Int) throws -> Int {
    if b == 0 {
        throw CustomError.someError
    }
    return a / b
}

Hata Yakalama: Bir hata fırlatıldığında, do, try, catch blokları kullanarak bu hatayı yakalayabilirsiniz. Örneğin:
do {
    let result = try divide(10, by: 0)
    print(result)
} catch CustomError.someError {
    print("Hata oluştu: someError")
} catch CustomError.anotherError {
    print("Hata oluştu: anotherError")
} catch {
    print("Bilinmeyen bir hata oluştu: \(error)")
}
Ayıklama: Ayıklama, kodunuzun hatalarını bulma ve düzeltme sürecidir. Xcode gibi Swift geliştirme ortamları, ayıklamayı kolaylaştıran araçlar sunar. 
Ayıklama yaparken aşağıdaki adımları izleyebilirsiniz:
a. Kodunuzda ayıklamak istediğiniz yere bir "breakpoint" ekleyin. Bu, kodun çalışmasını durduracak bir işarettir.
b. Uygulamanızı çalıştırın ve breakpoint'e geldiğinizde kodunuz duracaktır.
c. Xcode'daki "Debug Area" penceresini kullanarak değişken değerlerini izleyebilir ve hata ayıklama işlemini daha kolay hale getirebilirsiniz.
d. Adım adım kodunuzu çalıştırarak hata noktasını belirleyebilir ve sorunları tanımlayabilirsiniz.
e. Hataları düzelttikten sonra breakpoint'i kaldırabilir ve uygulamanızı sorunsuz bir şekilde çalıştırabilirsiniz.
Swift dilinde hataların işlenmesi ve ayıklanması, kodunuzu daha güvenilir ve istikrarlı hale getirmenize yardımcı olur. Ayıklama sürecinde Xcode gibi
geliştirme araçları büyük bir yardımcıdır, bu nedenle bu tür araçları kullanmayı öğrenmek önemlidir.






