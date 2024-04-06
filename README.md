import SwiftUI

struct Exo_partiel: View {
    var ensemble: Set<String> = ["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"]
    
    var body: some View {
        VStack {
            Text("Hello, World!")
            
            let (pairs, impairs) = trierPairsImpairs(ensemble)
            
            Text("Nombres pairs : \(pairs)")
            Text("Nombres impairs : \(impairs)")
        }
    }
}

struct Exo_partiel_Previews: PreviewProvider {
    static var previews: some View {
        Exo_partiel()
    }
}

func trierPairsImpairs(_ ensemble: Set<String>) -> (pairs: Set<String>, impairs: Set<String>) {
    var pairs = Set<String>()
    var impairs = Set<String>()
    
    for nombre in ensemble {
        if let nombreInt = Int(nombre) {
            if nombreInt % 2 == 0 {
                pairs.insert(nombre)
            } else {
                impairs.insert(nombre)
            }
        }
    }
    
    return (pairs, impairs)
}

