#Typescript

class List<T> {
    private dict: { [id: string]: T; } = {}
    private ids: Array<String>;

    constructor() {
        this.ids = [];
    }
    add(id: string, value: T): void {
        if (this.hasKey(id)) {
            debugger;
            return;
        }
        this.ids.push(id);
        this.dict[id] = value;
    }
    hasKey(id: string): boolean {
        return this.ids.indexOf(id) === -1 ? false : true;
    }
    size(): number {
        return this.ids.length;
    }
    get(id: string): T {
        return this.dict[id];
    }
    getIndex(id: string) : number {
        return this.ids.indexOf(id);
    }
    remove(id: string) {
        delete this.dict[id];
        let index: number = this.getIndex(id);
        this.ids.splice(index, 1);
    }
    insertFirst(id: string, value: T): void {
        if (this.hasKey(id)) {
            debugger;
            return;
        }
        this.ids.splice(0, 0, id);
        this.dict[id] = value;
    }
    insertAfter(id: string, idNew: string, valueNew: T): void {
        if (this.hasKey(id) == false) {
            debugger;
            return;
        }
        if (this.hasKey(idNew)) {
            debugger;
            return;
        }
        let index: number = this.getIndex(id) + 1;
        this.ids.splice(index, 0, idNew);
        this.dict[idNew] = valueNew;
    }
    //forEach(fkt: any) : void {
    //    this.keys.forEach(fkt);
    //}
    //sort(fkt: any): any {
    //    return this.keys.sort(fkt);
    //}
}
