# SwiftUI_Charts_Super_Basic

```swift
//
//  ContentView.swift
//  Swift_Charts
//
//  Created by paige shin on 2023/05/09.
//

import Charts
import SwiftUI

struct Item: Identifiable {
    var id = UUID()
    let type: String
    let value: Double
}

struct ContentView: View {

    let items = [
        Item(type: "Engineering", value: 100),
        Item(type: "Operations", value: 35),
        Item(type: "Design", value: 72),
        Item(type: "Sales", value: 22),
        Item(type: "Mgmt", value: 130),
    ]

    var body: some View {
        NavigationView {
            ScrollView {
                // bar, line, area, ruler, point
                Chart(self.items) { item in
                    BarMark(
                        x: .value("Department", item.type),
                        y: .value("Profit", item.value)
                    )
                    .foregroundStyle(Color.red.gradient)
                }
                .frame(height: 200)
                .padding()
                
                Chart(self.items) { item in
                    LineMark(
                        x: .value("Department", item.type),
                        y: .value("Profit", item.value)
                    )
                    .foregroundStyle(Color.blue.gradient)
                }
                .frame(height: 200)
                .padding()
                
                Chart(self.items) { item in
                    AreaMark(
                        x: .value("Department", item.type),
                        y: .value("Profit", item.value)
                    )
                    .foregroundStyle(Color.green.gradient)
                }
                .frame(height: 200)
                .padding()
                
                Chart(self.items) { item in
                    PointMark(
                        x: .value("Department", item.type),
                        y: .value("Profit", item.value)
                    )
                    .foregroundStyle(Color.pink.gradient)
                }
                .frame(height: 200)
                .padding()
                
                Chart(self.items) { item in
                    RuleMark(
                        x: .value("Department", item.type)
                    )
                    .foregroundStyle(Color.pink.gradient)
                }
                .frame(height: 200)
                .padding()
                
            } // SCROLL VIEW
            .navigationTitle("Charts")
        } // NAVIGATION VIEW
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

```
