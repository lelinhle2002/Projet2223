```py
def skim_up_bin_packing(items, bin_capacity):
    # Tri des articles par ordre décroissant de taille
    sorted_items = sorted(items, reverse=True)
    
    # Initialisation 
    bins = [[sorted_items[0]]]
    
   
    for item in sorted_items[1:]:
        min_waste = float("inf")
        best_bin_index = None
        for i in range(len(bins)):
            bin_waste = bin_capacity - sum(bins[i])
            if item <= bin_waste < min_waste:
                min_waste = bin_waste
                best_bin_index = i
        
        if best_bin_index is not None:
            bins[best_bin_index].append(item)
        else:
            bins.append([item])
    
    return bins


    ```
